# tests/

Test suites per [Test Plan](../docs/10-quality/test-plan.md).

```
tests/
├── unit/              # pure function tests (Dev-owned)
├── integration/       # API-level, vendors mocked (QA-owned)
├── contract/          # Response contract: summary derivable from detail
├── system/            # full loop against live cheap vendors
├── data/
│   ├── dispatcher/    # 60-case dispatcher set (20 A / 20 B / 20 fallback)
│   ├── skills/        # 20 × 3 skills = 60 functional cases
│   └── voice-ui/      # 10-case consistency audit
└── uat/               # scenario scripts for Customer role
```

Language split in every data set: EN 50% / JA 50%.
