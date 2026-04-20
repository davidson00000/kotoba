# src/

Source code. Populated starting Sprint 2 per [WBS](../docs/02-scope/wbs.md) and [TDD](../docs/07-design/tdd.md).

Planned layout (subject to ADR-005 on client stack):

```
src/
├── client/           # PTT capture + detail panel render
├── server/
│   ├── api/          # HTTP entrypoints
│   ├── orchestrator/ # intent + skill dispatch
│   ├── skills/       # per-skill modules implementing Skill interface
│   ├── stt/          # STT provider adapter
│   ├── tts/          # TTS provider adapter
│   └── llm/          # LLM provider adapter + fallback
└── shared/           # Response contract types, shared utils
```
