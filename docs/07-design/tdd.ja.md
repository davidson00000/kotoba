# 技術設計書 (Technical Design Document, TDD) — Kotoba

**オーナー:** リードエンジニア（Claude Code）
**ステータス:** ドラフト (v0.1)
**関連文書:** スコープ記述書、WBS §1.2および§1.4、ADR 001–00N

## 1. 概要

クライアント / サーバー構成。シンクライアントがマイク + スピーカー + 詳細パネル表示を担当し、バックエンドがオーケストレーションとスキル実行を担当する。MVPではリクエスト単位でステートレス。

## 2. ハイレベル・アーキテクチャ

```
[マイク] → [クライアント: PTTキャプチャ]
              │ 音声blob
              ▼
       [バックエンドAPI /query]
              │
              ├─> [STTプロバイダ]
              │       │ 転記テキスト
              │       ▼
              ├─> [オーケストレータ: インテント + スキルディスパッチ]
              │       │
              │       ├─ スキルマッチ → [スキルモジュール] ──┐
              │       └─ マッチなし → [LLMフォールバック] ────┤
              │                                               ▼
              │                                [レスポンスオブジェクト:
              │                                 summary_text + detail_payload]
              │
              ├─> [TTSプロバイダ] → 音声
              ▼
       [クライアント: 音声再生 + 詳細パネルのレンダリング]
```

## 3. コンポーネントの責務

| コンポーネント | 責務 | 主要インターフェース |
|---|---|---|
| クライアント | 音声I/O、PTT UX、詳細パネルのレンダリング | `POST /query (audio)` → `(audio, detail_json)` |
| STT | 音声 → テキスト | `stt(audio, lang) → transcript` |
| オーケストレータ | インテント解析、スキルルーティング、プロンプト構築 | `orchestrate(transcript) → Response` |
| スキルモジュール | ドメインタスクの実行、構造化データの返却 | `run(params) → {summary, detail}` |
| LLMフォールバック | スキルマッチがない場合の直接応答 | `llm(prompt) → {summary, detail}` |
| TTS | テキスト → 音声 | `tts(text, voice) → audio` |

## 4. 共有契約: `Response`

音声とUIの非同期（リスクR4）を防ぐ中核オブジェクト。

```json
{
  "summary_text": "文字列 ≤ 300文字、TTSが発話する内容",
  "detail_payload": {
    "type": "skill_result | general",
    "skill_id": "文字列 | null",
    "title": "文字列",
    "body": "markdownまたは構造化オブジェクト",
    "sources": ["url", ...]
  },
  "diagnostics": {
    "skill_confidence": 0.0,
    "latency_ms": 0,
    "cost_usd": 0.0
  }
}
```

ルール: `summary_text` は `detail_payload` から導出可能であること。契約テストで強制する。

## 5. スキルモジュール・インターフェース

```python
class Skill:
    id: str
    def matches(transcript: str) -> float  # 信頼度 0..1
    def run(params: dict) -> Response
```

ディスパッチャは閾値を超える中で最高信頼度のスキルを選択する。該当なしの場合はフォールバック。

## 6. デプロイ

クラウドプロバイダ: ADR-003で決定。候補: Fly.io、Railway、Cloud Run、Lambda。基準: アイドル時コストの低さ、コールドスタート速度、シークレット管理の簡便さ。

## 7. 可観測性 (Observability)

- リクエスト単位の構造化ログ（request_id、skill_id、レイテンシ、コスト）
- 日次コスト集計 → コストダッシュボード（MVPは追記型のログで十分）

## 8. セキュリティ

- APIキーはプラットフォームのシークレットのみに保管、リポジトリには一切入れない
- `Authorization` ヘッダーで単一ユーザートークンを使用
- PII（個人識別情報）は保持しない

## 9. 未決事項（→ ADR化）

- ADR-001: LLMプロバイダの選定
- ADR-002: STT/TTSベンダーの選定
- ADR-003: デプロイ先の選定
- ADR-004: スキルディスパッチ機構（キーワード / 埋め込み / LLM分類器）
- ADR-005: クライアントスタック（Web / デスクトップ）

## 10. 改訂履歴

| バージョン | 日付 | 執筆者 | 変更内容 |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | リードエンジニア | 初版ドラフト |
