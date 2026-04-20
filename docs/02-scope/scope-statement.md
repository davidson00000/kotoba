# Scope Statement — Kotoba

## Product Scope Description

A voice-driven personal assistant. User speaks a request; system replies with (a) a spoken summary via TTS and (b) a rich visual detail panel on screen. Core pipeline: STT → intent/LLM orchestration → skill execution → synthesized response (voice + UI).

## Product Acceptance Criteria

1. End-to-end latency (voice-in to voice-out start) ≤ 5 seconds for skill-free LLM queries.
2. At least **3 skills** working reliably (≥ 90% success on a 20-case test set per skill).
3. Deployed backend reachable from a second machine.
4. Voice and on-screen output always consistent (no contradiction between spoken summary and displayed detail).

## Deliverables

| # | Deliverable | Acceptance |
|---|---|---|
| D1 | STT module | Handles EN + JA input, < 2s transcription on a 10s clip |
| D2 | LLM orchestrator | Skill dispatch + fallback to pure LLM answer |
| D3 | 3 skills (initial list — TBD, examples: Calendar, Weather, Web search) | Each passes its test set |
| D4 | TTS + UI panel | Synchronized; panel renders structured data |
| D5 | Cloud backend | Deployed, logs + cost dashboard |
| D6 | PMBOK artifact set | All 17 artifacts populated and current |

## Exclusions

- Mobile native apps
- Multi-tenant / multi-user
- Wake-word ("Hey Kotoba") — use push-to-talk for MVP
- Long-term memory across sessions (MVP = stateless)
- Custom fine-tuning

## Constraints

- Budget: ≤ $60/mo cloud + API during UAT
- Time: 12 weeks to Closing
- Team: One human + six AI agents
- Tech: Must run on Kosuke's existing laptop for dev

## Assumptions

- Anthropic/OpenAI API remains available and within cost envelope.
- Browser ChatGPT and Claude remain accessible as stakeholder proxies.
- No regulatory scope (personal project, no end-user data collection).

## Change Control

Any change to this document requires a Change Request logged in `docs/09-change/change-log.md` with rationale and impact assessment. Scope creep is the #1 risk — say no by default.
