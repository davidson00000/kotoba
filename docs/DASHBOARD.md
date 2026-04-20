# Program Dashboard — Kotoba

**As of:** 2026-04-20 (update weekly)
**TPM:** Kosuke Nakamura
**日本語版:** [DASHBOARD.ja.md](DASHBOARD.ja.md)

---

## Where are we in PMBOK?

```
  [●] Initiating  →  [ ] Planning  →  [ ] Executing  →  [ ] Closing
                                      ↕
                                 [ ] Monitoring & Controlling
```

Current phase: **Initiating** — finishing the Charter and Stakeholder Register; Planning artifacts drafted but not yet baselined.

Next phase gate: **M2 — Planning baseline (Week 3)**. Exit criteria: Scope, WBS, Schedule, Risk, Comms, Quality, TDD all at v1.0.

---

## Sprint & Milestone

| Item | Value |
|---|---|
| Current sprint | **S1** (Weeks 1–2) |
| Current week | Week ? (set at kickoff) |
| Sprint goal | Complete Initiating, baseline Planning artifacts |
| Next milestone | **M1** — Charter + Stakeholder Register approved, end of Week 1 |
| Weeks to Closing (M7) | 12 |

---

## RAG Snapshot

| Dimension | Status | Note |
|---|---|---|
| Schedule | 🟢 | Not started; charter-ready |
| Scope | 🟢 | Frozen at 3 skills per Scope Statement |
| Cost | 🟢 | $0 spent; caps: $30/mo dev, $60/mo UAT |
| Quality | ⚪ | N/A — no code yet |
| Risk | 🟡 | R2 (scope creep) and R5 (bus factor) top of list |

Legend: 🟢 on track / 🟡 watch / 🔴 breach / ⚪ not applicable yet.

---

## This Week — Who Does What

| Role | Agent | Action this week |
|---|---|---|
| TPM / PO | Kosuke | Approve Charter; write ADR-001 (LLM provider); set sprint 1 dates |
| External Reviewer | Browser ChatGPT | Review Charter + Scope, return pushback |
| Customer (scenarios) | Browser Claude | Draft 5 additional scenarios per US-001..US-005 |
| Customer (voice UAT) | Kosuke | — (no build yet) |
| Lead Engineer | Claude Code | Draft ADR-001 with TPM; review TDD v0.1 |
| Dev | Codex Desktop | — (sprint 2 start) |
| QA | Antigravity IDE | Draft test set template for dispatcher |
| PMO | Claude Cowork | Keep artifacts current; flag stale dates |

Update this table at every sprint review.

---

## Top 3 Risks

| ID | Risk | Score | Delta | Action owner |
|---|---|---|---|---|
| R2 | Scope creep beyond 3 skills | 16 | → | TPM |
| R5 | Bus factor = 1 | 15 | → | TPM |
| R7 | PMP study (May) consumes TPM bandwidth | 12 | → | TPM |

Full register: [docs/04-risk/risk-register.md](04-risk/risk-register.md)

---

## Open Items

| Type | Count | Link |
|---|---|---|
| Change Requests (approved, not yet implemented) | 0 | [change-log.md](09-change/change-log.md) |
| Defects S1/S2 open | 0 | [defect-log.md](10-quality/defect-log.md) |
| ADRs pending decision | 5 (001–005) | [adr/](07-design/adr/) |

---

## Next Decisions Required

Ordered by blocking weight.

1. **ADR-001 LLM provider** — blocks orchestrator implementation (Sprint 3) and cost model (R1)
2. **ADR-002 STT/TTS vendor** — blocks voice loop (Sprint 2)
3. **Skill list finalized** — blocks Scope baseline (M2). Currently placeholder "calendar / weather / web search"
4. **ADR-003 deployment target** — blocks Sprint 5
5. **ADR-005 client stack** — Web or desktop; affects UI panel work (Sprint 4)

---

## How to update this dashboard

Weekly, during Status Report authoring:
1. Change `As of` date.
2. Move the phase marker `[●]` if a phase gate has been crossed.
3. Update RAG and the "This Week" table.
4. Update Open Items counts.
5. Adjust Top 3 Risks if ordering changed.

Commit in the same commit as the week's Status Report.
