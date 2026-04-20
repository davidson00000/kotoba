# Project Charter — Kotoba

**Project Name:** Kotoba — Personal AI Voice Assistant
**Charter Version:** 0.1 (Draft)
**Date:** YYYY-MM-DD
**Sponsor:** Kosuke Nakamura (self-funded)
**TPM:** Kosuke Nakamura

---

## 1. Purpose / Business Case

Build a Jarvis-style voice assistant (spoken summary + on-screen detail) as a vehicle to (a) deliver a working AI/cloud product and (b) demonstrate PMBOK-based program management of an AI/cloud initiative for career transition evidence.

## 2. Objectives (SMART)

| # | Objective | Measure | Target Date |
|---|---|---|---|
| O1 | Working voice→LLM→voice+screen loop | End-to-end demo video | MVP + 8 weeks |
| O2 | Cloud-deployed backend | Public endpoint reachable | MVP + 8 weeks |
| O3 | All PMBOK artifacts kept current | 100% of artifact slots populated and updated within the sprint they belong to | Ongoing |
| O4 | GitHub repo auditable | All commits tied to Change Log or Sprint | Ongoing |

## 3. In Scope

- Voice input (STT)
- LLM orchestration (Anthropic API or equivalent)
- Voice output (TTS) + synchronized on-screen detail panel
- At least 3 concrete skills (e.g., calendar lookup, weather, web search) — TBD in Scope Statement
- Cloud deployment of backend
- Full PMBOK artifact set

## 4. Out of Scope (initial)

- Mobile app packaging
- Multi-user accounts / auth beyond a single-user token
- Custom wake-word training
- Hardware (Raspberry Pi, smart speaker integration)
- Fine-tuned custom models

## 5. High-Level Milestones

| Milestone | Target |
|---|---|
| M1: Charter + Stakeholder Register signed off | Week 1 |
| M2: Scope, WBS, TDD, Risk baseline | Week 3 |
| M3: MVP (local loop only) | Week 6 |
| M4: Cloud deployment | Week 10 |
| M5: UAT + Closing | Week 12 |

## 6. Budget (cloud cost)

Target monthly cloud + API spend cap: **$30/month** during dev, **$60/month** during UAT. Tracked in `docs/10-quality/` cost section (TBD — add if scope grows).

## 7. Top Risks (seed — full list in Risk Register)

| ID | Risk | Initial Response |
|---|---|---|
| R1 | LLM API cost overrun | Set hard monthly cap + alerting |
| R2 | Scope creep (endless "skills") | Freeze skill list at Scope baseline |
| R3 | Single-person bus factor | Every artifact committed; no local-only state |

## 8. Success Criteria

1. A user (Customer role) can complete at least 3 distinct task types via voice.
2. All 17 PMBOK artifacts exist, are current, and are reviewed at Closing.
3. Lessons Learned document is produced and publishable.

## 9. Approval

| Role | Name | Signature | Date |
|---|---|---|---|
| Sponsor | Kosuke Nakamura | | |
| TPM | Kosuke Nakamura | | |
