# Risk Register — Kotoba

Probability / Impact on 1–5 scale. Score = P × I. Review cadence: every sprint review.

| ID | Category | Description | P | I | Score | Response Strategy | Action | Owner | Status |
|----|---|---|---|---|---|---|---|---|---|
| R1 | Cost | LLM/STT/TTS API cost exceeds $60/mo cap | 3 | 4 | 12 | Mitigate | Set hard cap + daily cost log + model-tier selection in ADR | TPM | Open |
| R2 | Scope | Skill list expands beyond 3 | 4 | 4 | 16 | Mitigate | Freeze at Scope baseline; Change Request required for additions | TPM | Open |
| R3 | Technical | STT latency > 2s on JA input | 3 | 3 | 9 | Mitigate | Benchmark 2 providers in ADR-002 before committing | Lead Eng | Open |
| R4 | Technical | Voice/UI desync (spoken ≠ displayed) | 3 | 4 | 12 | Mitigate | Shared contract object between TTS and UI render | Lead Eng | Open |
| R5 | Resource | Single human operator (bus factor = 1) | 5 | 3 | 15 | Mitigate | All state committed to repo; no local-only artifacts | TPM | Open |
| R6 | External | LLM API pricing change | 2 | 4 | 8 | Accept + Monitor | Quarterly review; provider-abstraction in orchestrator | Lead Eng | Open |
| R7 | Schedule | PMP study (May) consumes TPM bandwidth | 4 | 3 | 12 | Mitigate | Planning sprint front-loaded; sprints 3–4 light-touch | TPM | Open |
| R8 | Quality | AI-generated code quality drift (hallucinated APIs) | 4 | 3 | 12 | Mitigate | Dev/QA separation; all code must pass Antigravity test set | QA | Open |
| R9 | Security | API keys leaked to repo | 2 | 5 | 10 | Avoid | .env + pre-commit hook + secrets in deploy platform only | Lead Eng | Open |
| R10 | Stakeholder | Customer (Browser Claude) scope drift across sessions | 4 | 2 | 8 | Mitigate | Baseline requirements frozen in user-stories.md; new requests → Change Log | TPM | Open |

## Top 3 (by score)

1. **R2 Scope creep** (16) — hardest risk for any PM, especially one-person.
2. **R5 Bus factor** (15) — mitigated by repo discipline.
3. **R7 PMP bandwidth** (12) and R1 / R4 / R8 tied.

## Change log

| Date | Change |
|---|---|
| YYYY-MM-DD | Initial register, 10 risks identified |
