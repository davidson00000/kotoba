# Schedule / Milestones — Kotoba

12-week program. 2-week sprints. Sprint review = Friday; Retro + next Sprint Plan = same day.

## Milestones

| ID | Milestone | Week | Exit Criteria |
|---|---|---|---|
| M1 | Initiating complete | 1 | Charter + Stakeholder Register approved |
| M2 | Planning baseline | 3 | Scope / WBS / Schedule / Risk / Comms / Quality / TDD all at v1.0 |
| M3 | MVP local | 6 | Voice loop works on laptop; 1 skill passes |
| M4 | All 3 skills | 8 | 3 skills each ≥ 90% pass rate |
| M5 | Cloud deploy | 10 | Public endpoint reachable + cost dashboard live |
| M6 | UAT complete | 11 | Customer (Browser Claude) signs off UAT report |
| M7 | Closing | 12 | Lessons Learned + Final Report + GitHub tag `v1.0` |

## Sprint calendar

| Sprint | Weeks | Focus |
|---|---|---|
| S1 | 1–2 | Initiating + Planning kickoff |
| S2 | 3–4 | TDD + STT/TTS skeleton |
| S3 | 5–6 | LLM orchestrator + Skill 1 → MVP local |
| S4 | 7–8 | Skills 2 & 3 + UI panel |
| S5 | 9–10 | Cloud deploy + hardening |
| S6 | 11–12 | UAT + Closing |

## Critical path (rough)

Charter → TDD → LLM Orchestrator → Skill dispatcher → Skill 1 → Cloud deploy → UAT

Any slip in orchestrator or deploy hits the finish line 1:1. Buffer is in Sprint 5.

## Tracking

Actuals recorded in weekly Status Reports (`docs/08-execution/status-reports/`). Schedule variance > 20% triggers a Change Request.
