# Work Breakdown Structure — Kotoba

Decomposed to work-package level (100% rule; each child fully covers its parent).

```
1.0  Kotoba Program
├── 1.1  Project Management
│   ├── 1.1.1  Charter & Stakeholder setup
│   ├── 1.1.2  Planning artifacts (Scope, WBS, Schedule, Risk, Comms, Quality)
│   ├── 1.1.3  Sprint management (plans + status reports)
│   ├── 1.1.4  Change control
│   └── 1.1.5  Closing (Lessons Learned, Final Report)
├── 1.2  Architecture & Design
│   ├── 1.2.1  Technical Design Document (TDD)
│   ├── 1.2.2  ADRs (LLM provider, STT/TTS vendor, deployment target, data flow)
│   └── 1.2.3  Cost model
├── 1.3  Voice I/O
│   ├── 1.3.1  STT integration
│   ├── 1.3.2  TTS integration
│   └── 1.3.3  Push-to-talk UX
├── 1.4  LLM Orchestration
│   ├── 1.4.1  Prompt layer
│   ├── 1.4.2  Skill dispatcher
│   └── 1.4.3  Fallback / error handling
├── 1.5  Skills (MVP set — 3 skills, exact list TBD)
│   ├── 1.5.1  Skill A
│   ├── 1.5.2  Skill B
│   └── 1.5.3  Skill C
├── 1.6  UI / Detail Panel
│   ├── 1.6.1  Layout + component library choice
│   ├── 1.6.2  Structured-data rendering
│   └── 1.6.3  Voice/UI sync
├── 1.7  Cloud Deployment
│   ├── 1.7.1  Backend hosting
│   ├── 1.7.2  Secrets / API key mgmt
│   ├── 1.7.3  Logging + cost dashboard
│   └── 1.7.4  Basic auth / single-user token
├── 1.8  Quality Assurance
│   ├── 1.8.1  Test plan
│   ├── 1.8.2  Skill test sets (20 cases × 3 skills)
│   ├── 1.8.3  Defect log management
│   └── 1.8.4  UAT
└── 1.9  Documentation & Repo Hygiene
    ├── 1.9.1  README maintenance
    ├── 1.9.2  ADR discipline
    └── 1.9.3  Final audit pre-Closing
```

## WBS Dictionary (sample — fill per work package as work starts)

| ID | Name | Description | Deliverable | Owner | Estimate |
|---|---|---|---|---|---|
| 1.2.1 | TDD | End-to-end technical design, all interfaces | `docs/07-design/tdd.md` | Claude Code (Lead Eng) | 3 d |
| 1.4.2 | Skill dispatcher | Routes intent → skill module | Code + unit tests | Codex (Dev) | 5 d |
| 1.8.2 | Skill test sets | 20 cases per skill, pass/fail rubric | `tests/skills/*` | Antigravity (QA) | 3 d |
