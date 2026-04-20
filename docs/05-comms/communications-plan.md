# Communications Plan — Kotoba

## Principle

Every cross-agent exchange that alters a baseline (scope, schedule, design, quality) is captured in a repo artifact. Chat sessions are ephemeral; the repo is the source of truth.

## Communication Matrix

| What | To whom | From | Frequency | Channel | Artifact |
|---|---|---|---|---|---|
| Status Report | Sponsor (self), External Reviewer (ChatGPT) | TPM | Weekly (Fri) | Repo + ChatGPT paste | `docs/08-execution/status-reports/week-NN.md` |
| Sprint Plan | All agents | TPM | Bi-weekly | Repo | `docs/08-execution/sprints/sprint-NN-plan.md` |
| Sprint Review + Retro | All agents | TPM | End of sprint | Chat sessions, summary in Status Report | Status Report + Lessons Learned |
| Change Request | Sponsor / PO | Requester | As needed | Repo | `docs/09-change/change-log.md` entry |
| Design decision | Lead Eng → TPM + Dev + QA | Lead Eng | Per decision | Repo | ADR in `docs/07-design/adr/` |
| Defect report | Lead Eng + Dev | QA | Per defect | Repo | `docs/10-quality/defect-log.md` |
| Requirements update | All | Customer (Browser Claude) via TPM | As needed | Repo | `docs/06-requirements/user-stories.md` |
| Risk update | Sponsor | TPM | Weekly (in Status) + sprint review | Repo | `docs/04-risk/risk-register.md` |

## Escalation Path

Dev blocker → Lead Engineer → TPM → Sponsor. Since Sponsor = TPM, escalation to Sponsor means: stop, write it down as a Change Request, sleep on it, decide the next day.

## Review Cadence Summary

- Daily: none (solo + agents, but work log in commits)
- Weekly: Status Report
- Bi-weekly: Sprint Review + Retro + next Sprint Plan
- Monthly: External Reviewer (ChatGPT) consult — paste Status Reports + ask for pushback
- End of program: Closing artifacts

## Language

English for all repo artifacts (CV audience). Japanese OK in chat sessions.
