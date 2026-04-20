# Kotoba — Personal AI Assistant

🇯🇵 **日本語版:** [README.ja.md](README.ja.md)

A Jarvis-style (Iron Man) AI assistant: user speaks to it, it replies verbally with a summary while displaying rich details on screen. Inspired by [open-jarvis/OpenJarvis](https://github.com/open-jarvis/OpenJarvis).

This repository is managed as a **PMBOK-compliant program**. The goal is twofold:

1. Build a working AI/cloud assistant.
2. Demonstrate end-to-end Technical Program Management of an AI/cloud initiative, with every PMBOK artifact version-controlled and auditable.

**Program Dashboard:** [docs/DASHBOARD.md](docs/DASHBOARD.md) — current phase, sprint, RAG, who's doing what this week.

---

## PMBOK Artifact Map

| Process Group | Artifact | Path |
|---|---|---|
| Initiating | Project Charter | [docs/00-charter/project-charter.md](docs/00-charter/project-charter.md) |
| Initiating | Stakeholder Register | [docs/01-stakeholders/stakeholder-register.md](docs/01-stakeholders/stakeholder-register.md) |
| Planning | Scope Statement | [docs/02-scope/scope-statement.md](docs/02-scope/scope-statement.md) |
| Planning | WBS | [docs/02-scope/wbs.md](docs/02-scope/wbs.md) |
| Planning | Milestone Schedule | [docs/03-schedule/milestones.md](docs/03-schedule/milestones.md) |
| Planning | Risk Register | [docs/04-risk/risk-register.md](docs/04-risk/risk-register.md) |
| Planning | Communications Plan | [docs/05-comms/communications-plan.md](docs/05-comms/communications-plan.md) |
| Planning | User Stories / Requirements | [docs/06-requirements/user-stories.md](docs/06-requirements/user-stories.md) |
| Planning | Technical Design (TDD) | [docs/07-design/tdd.md](docs/07-design/tdd.md) |
| Planning | Architecture Decision Records | [docs/07-design/adr/](docs/07-design/adr/) |
| Planning | Quality / Test Plan | [docs/10-quality/test-plan.md](docs/10-quality/test-plan.md) |
| Executing | Sprint Plans | [docs/08-execution/sprints/](docs/08-execution/sprints/) |
| M&C | Status Reports | [docs/08-execution/status-reports/](docs/08-execution/status-reports/) |
| M&C | Change Log | [docs/09-change/change-log.md](docs/09-change/change-log.md) |
| M&C | Defect Log | [docs/10-quality/defect-log.md](docs/10-quality/defect-log.md) |
| Closing | Lessons Learned | [docs/11-closing/lessons-learned.md](docs/11-closing/lessons-learned.md) |
| Closing | Final Report | [docs/11-closing/final-report.md](docs/11-closing/final-report.md) |

Every artifact has a Japanese companion at `*.ja.md`.

---

## Team & Roles

Stakeholders played by AI agents where possible; human (Kosuke) holds TPM.

| PMBOK Role | Played by | Access |
|---|---|---|
| Technical Program Manager + Product Owner | Kosuke (human) | — |
| External Reviewer / Sponsor proxy | Browser ChatGPT | Conversation only |
| Customer — scenarios & UAT review | Browser Claude | Conversation only |
| Customer — real voice UAT | Kosuke (human) | Real mic / speaker |
| Lead Engineer / Architect | Claude Code | Local + execution |
| Coder (Dev) | Codex Desktop | Local + execution |
| QA / Tester | Google Antigravity IDE | Local + execution + browser automation |
| PMO / Doc Keeper | Claude Cowork | Local visible |

**Separation of duties:**
- **PO ≠ Customer**: TPM/PO sets priority; Customer role supplies user voice and UAT evidence.
- **Dev ≠ QA**: Codex writes code; Antigravity independently tests, using browser automation as its differentiator.
- **Architect ≠ Dev**: Claude Code defines patterns and reviews; Codex implements.
- **Customer split**: AI handles scenario authoring and text-layer review; the only true end-user test (voice in / voice out) is done by a human, because no AI in this team can physically use a microphone or speaker. This is an honest design choice, not a gap.

---

## CV / Interview Statement

> Led a personal AI/cloud initiative (Kotoba voice assistant) as Technical Program Manager, following PMBOK process groups end-to-end. Produced and version-controlled all standard artifacts — Charter, Stakeholder Register, Scope, WBS, Schedule, Risk Register, Communications Plan, TDD with ADRs, Quality Plan, Sprint Plans, Status Reports, Change Log, Lessons Learned, Final Report. Orchestrated a distributed team of six AI collaborators (ChatGPT, Claude browser, Claude Code, Codex Desktop, Antigravity IDE, Claude Cowork) across Architecture, Dev, QA, Customer, Review, and PMO roles, enforcing separation of duties (Dev ≠ QA, PO ≠ Customer) and change control. Delegated documentation maintenance to a dedicated PMO agent so the TPM role stayed focused on decisions. Repository: https://github.com/davidson00000/kotoba

---

## Status

Phase: **Initiating** (Charter draft).
