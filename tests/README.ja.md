# tests/

[テスト計画書](../docs/10-quality/test-plan.ja.md)に従うテストスイート。

```
tests/
├── unit/              # 純粋関数のテスト（開発担当）
├── integration/       # APIレベル・ベンダーはモック化（QA担当）
├── contract/          # Response契約テスト：サマリが詳細から導出可能であること
├── system/            # 安価なベンダーに対するフルループ実行
├── data/
│   ├── dispatcher/    # ディスパッチャ60ケース (skill_A 20 / skill_B 20 / フォールバック 20)
│   ├── skills/        # スキルごと20ケース × 3スキル = 60ケース
│   └── voice-ui/      # 音声とUIの整合性監査10ケース
└── uat/               # Customerロール用シナリオスクリプト
```

すべてのデータセットにおける言語分布: 英語50% / 日本語50%。
