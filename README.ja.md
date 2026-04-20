# Kotoba — パーソナルAIアシスタント

Jarvisスタイル（『アイアンマン』のAI）のアシスタント: ユーザーが話しかけると、システムは口頭で要約を返しつつ画面上にリッチな詳細を表示する。インスピレーション元: [open-jarvis/OpenJarvis](https://github.com/open-jarvis/OpenJarvis)。

本リポジトリは **PMBOK準拠のプログラム**として運営される。目的は2つ:

1. 動作するAI/クラウドアシスタントを構築する。
2. AI/クラウドのイニシアチブに対するエンドツーエンドの技術プログラムマネジメントを実演する。すべてのPMBOK成果物はバージョン管理下に置かれ、監査可能である。

---

## PMBOK成果物マップ

| プロセス群 | 成果物 | パス |
|---|---|---|
| 立上げ | プロジェクト憲章 | [docs/00-charter/project-charter.ja.md](docs/00-charter/project-charter.ja.md) |
| 立上げ | ステークホルダー登録簿 | [docs/01-stakeholders/stakeholder-register.ja.md](docs/01-stakeholders/stakeholder-register.ja.md) |
| 計画 | スコープ記述書 | [docs/02-scope/scope-statement.ja.md](docs/02-scope/scope-statement.ja.md) |
| 計画 | WBS | [docs/02-scope/wbs.ja.md](docs/02-scope/wbs.ja.md) |
| 計画 | マイルストーン・スケジュール | [docs/03-schedule/milestones.ja.md](docs/03-schedule/milestones.ja.md) |
| 計画 | リスク登録簿 | [docs/04-risk/risk-register.ja.md](docs/04-risk/risk-register.ja.md) |
| 計画 | コミュニケーション計画 | [docs/05-comms/communications-plan.ja.md](docs/05-comms/communications-plan.ja.md) |
| 計画 | ユーザーストーリー / 要件 | [docs/06-requirements/user-stories.ja.md](docs/06-requirements/user-stories.ja.md) |
| 計画 | 技術設計書 (TDD) | [docs/07-design/tdd.ja.md](docs/07-design/tdd.ja.md) |
| 計画 | アーキテクチャ決定記録 (ADR) | [docs/07-design/adr/](docs/07-design/adr/) |
| 計画 | 品質 / テスト計画書 | [docs/10-quality/test-plan.ja.md](docs/10-quality/test-plan.ja.md) |
| 実行 | スプリント計画 | [docs/08-execution/sprints/](docs/08-execution/sprints/) |
| 監視・コントロール | ステータスレポート | [docs/08-execution/status-reports/](docs/08-execution/status-reports/) |
| 監視・コントロール | 変更ログ | [docs/09-change/change-log.ja.md](docs/09-change/change-log.ja.md) |
| 監視・コントロール | 欠陥ログ | [docs/10-quality/defect-log.ja.md](docs/10-quality/defect-log.ja.md) |
| 終結 | 教訓 | [docs/11-closing/lessons-learned.ja.md](docs/11-closing/lessons-learned.ja.md) |
| 終結 | 終結レポート | [docs/11-closing/final-report.ja.md](docs/11-closing/final-report.ja.md) |

**プログラムダッシュボード**: [docs/DASHBOARD.ja.md](docs/DASHBOARD.ja.md)

---

## チームと役割

可能な限りAIエージェントにステークホルダーを演じさせ、人間（Kosuke）がTPMを担う。

| PMBOK役割 | 担当 | アクセス |
|---|---|---|
| 技術プログラムマネージャー + プロダクトオーナー | Kosuke（人間） | — |
| 外部レビュアー / スポンサー代理 | Browser ChatGPT | チャットのみ |
| Customer — シナリオ + UATレビュー | Browser Claude | チャットのみ |
| Customer — 実音声UAT | Kosuke（人間） | 実マイク / 実スピーカー |
| リードエンジニア / アーキテクト | Claude Code | ローカル + 実行 |
| コーダー (Dev) | Codex Desktop | ローカル + 実行 |
| QA / テスター | Google Antigravity IDE | ローカル + 実行 + ブラウザ自動化 |
| PMO / 文書管理者 | Claude Cowork | ローカル参照可 |

**職務分離:**
- **PO ≠ Customer**: TPM/POが優先順位、Customerロールがユーザーの声とUAT証跡を提供。
- **Dev ≠ QA**: Codexがコードを書き、Antigravityが独立してテスト（ブラウザ自動化を差別化要素として活用）。
- **Architect ≠ Dev**: Claude Codeがパターンを定義・レビュー、Codexが実装。
- **Customer分割**: AIはシナリオ作成とテキストレイヤーのレビューを担当。真のエンドユーザーテスト（音声の入出力）は、マイクやスピーカーを物理的に使えるメンバーがチーム内に人間1名しかいないため、人間が担当する。これはギャップを隠すのではなく、設計上の選択として明示している。

---

## CV / 面接用ステートメント

> パーソナルなAI/クラウドのイニシアチブ（Kotoba音声アシスタント）を、技術プログラムマネージャー (TPM) としてPMBOKのプロセス群に準拠した形でエンドツーエンドに推進した。標準成果物（憲章、ステークホルダー登録簿、スコープ、WBS、スケジュール、リスク登録簿、コミュニケーション計画、ADR付きTDD、品質計画、スプリント計画、ステータスレポート、変更ログ、教訓、終結レポート）をすべて作成・バージョン管理した。6体のAIコラボレータ（ChatGPT、Claudeブラウザ、Claude Code、Codex Desktop、Antigravity IDE、Claude Cowork）から成る分散チームを、アーキテクチャ・開発・QA・カスタマー・レビュー・PMOの各役割に割り当て、Dev ≠ QA、PO ≠ Customer 等の職務分離と変更管理を徹底した。ドキュメント維持は専任PMOエージェントに委譲することで、TPMは意思決定に集中できる体制を構築した。リポジトリ: github.com/\<user\>/kotoba

---

## 言語

このファイルは日本語版。英語版は [README.md](README.md)。

## ステータス

フェーズ: **立上げ (Initiating)**（憲章ドラフト中）。
