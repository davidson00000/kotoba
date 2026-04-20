# Stakeholder Register — Kotoba

Classification: Salience model (Power / Interest / Influence).

| ID | Name / Agent | Role | Power | Interest | Engagement Strategy | Primary Channel |
|----|---|---|---|---|---|---|
| S1 | Kosuke Nakamura | Sponsor / TPM / PO | High | High | Manage closely (self) | Direct |
| S2 | Kosuke Nakamura | Customer — real voice UAT | High | High | Own the only end-to-end human test | Real mic / speaker |
| S3 | Browser ChatGPT | External Reviewer / Sponsor proxy | Med | High | Consult at each baseline + monthly | Chat session, log excerpts to repo |
| S4 | Browser Claude | Customer — scenarios & UAT review | Low | High | Drives user stories + text-layer UAT review | Chat session |
| S5 | Claude Code | Lead Engineer / Architect | Med | High | Consult on TDD, ADRs, reviews | Chat + repo |
| S6 | Codex Desktop | Coder (Dev) | Low | Med | Task-driven via Sprint Plan | Repo |
| S7 | Antigravity IDE | QA / Tester | Low | Med | Task-driven via Test Plan; owns browser-based checks | Repo + IDE browser |
| S8 | Claude Cowork | PMO / Doc Keeper | Low | Med | Delegated artifact maintenance | Repo |
| S9 | End users (future) | Eventual adopters | Low | Unknown | Monitor (not yet engaged) | — |

## Role rationale (why each agent fits its slot)

- **S5 Claude Code → Lead Engineer**: agentic coding + repo awareness = best at holding architectural context across the codebase.
- **S6 Codex Desktop → Dev**: local execution, solid at coding tasks, no browser automation advantage to waste here.
- **S7 Antigravity IDE → QA**: its differentiator — browser automation — is exactly what system-level testing of a voice+UI app needs. Using Antigravity as Dev would leave that capability on the table.
- **S4 Browser Claude → Customer (scenarios)**: good at authoring varied user narratives and reviewing text-layer behavior. It cannot physically use a microphone, which is why…
- **S2 Kosuke → Customer (real voice UAT)**: the one piece of UAT no AI in this team can perform. Explicitly assigned to a human so the gap is documented, not hidden.
- **S8 Claude Cowork → PMO**: Cowork is designed for non-developer file and task workflows. Delegating artifact maintenance keeps the TPM focused on decisions, not doc upkeep.

## Separation of duties

- **PO ≠ Customer**: Kosuke-as-PO sets priority; Customer role (split S2 / S4) supplies user voice. PO may reject Customer asks — tradeoffs logged in Change Log.
- **Dev ≠ QA**: Codex (S6) writes code; Antigravity (S7) independently tests, including browser-automated system tests. Neither signs off the other's work.
- **Architect ≠ Dev**: Claude Code (S5) sets patterns and reviews; Codex implements.
- **PMO ≠ TPM**: Cowork (S8) maintains artifacts; TPM (S1) makes decisions and approves baseline changes.

## Known structural limits (documented, not hidden)

- Browser Claude and Browser ChatGPT are conversational only — they cannot read the local repo directly. Relevant excerpts are pasted into their sessions when needed.
- No AI in the team can use a microphone or speaker, so the final voice UAT is human-only (S2).
- Single human operator (bus factor = 1) — mitigated by keeping all state in the repo (see Risk R5).

## Change log

| Date | Change |
|---|---|
| YYYY-MM-DD | Initial register created |
| YYYY-MM-DD | Customer role split into scenarios (Browser Claude) and real voice UAT (Kosuke); Dev ↔ QA swapped — Codex = Dev, Antigravity = QA — to put Antigravity's browser automation on the QA side where it adds most value |
