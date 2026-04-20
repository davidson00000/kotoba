# Technical Design Document (TDD) — Kotoba

**Owner:** Lead Engineer (Claude Code)
**Status:** Draft (v0.1)
**Related:** Scope Statement, WBS §1.2 and §1.4, ADRs 001–00N

## 1. Overview

Client-server architecture. Thin client handles mic + speaker + detail panel render; backend runs orchestration and skill execution. Stateless per-request for MVP.

## 2. High-Level Architecture

```
[Mic] → [Client: PTT capture]
          │ audio blob
          ▼
     [Backend API /query]
          │
          ├─> [STT provider]
          │       │ transcript
          │       ▼
          ├─> [Orchestrator: intent + skill dispatch]
          │       │
          │       ├─ skill match → [Skill module] ──┐
          │       └─ no match → [LLM fallback] ─────┤
          │                                         ▼
          │                            [Response object:
          │                             summary_text + detail_payload]
          │
          ├─> [TTS provider] → audio
          ▼
   [Client: play audio + render detail panel]
```

## 3. Component Responsibilities

| Component | Responsibility | Key interface |
|---|---|---|
| Client | Audio I/O, PTT UX, detail panel render | `POST /query (audio)` → `(audio, detail_json)` |
| STT | Speech → text | `stt(audio, lang) → transcript` |
| Orchestrator | Intent parse, skill routing, prompt construction | `orchestrate(transcript) → Response` |
| Skill module | Execute a domain task, return structured data | `run(params) → {summary, detail}` |
| LLM fallback | Direct answer when no skill matches | `llm(prompt) → {summary, detail}` |
| TTS | Text → speech | `tts(text, voice) → audio` |

## 4. Shared Contract: `Response`

The core object preventing voice/UI desync (Risk R4).

```json
{
  "summary_text": "string ≤ 300 chars, what TTS speaks",
  "detail_payload": {
    "type": "skill_result | general",
    "skill_id": "string|null",
    "title": "string",
    "body": "markdown or structured object",
    "sources": ["url", ...]
  },
  "diagnostics": {
    "skill_confidence": 0.0,
    "latency_ms": 0,
    "cost_usd": 0.0
  }
}
```

Rule: `summary_text` must be derivable from `detail_payload`. Enforced by a contract test.

## 5. Skill Module Interface

```python
class Skill:
    id: str
    def matches(transcript: str) -> float  # confidence 0..1
    def run(params: dict) -> Response
```

Dispatcher picks highest confidence > threshold; else falls back.

## 6. Deployment

Cloud provider: TBD in ADR-003. Candidates: Fly.io, Railway, Cloud Run, Lambda. Criteria: low idle cost, fast cold start, simple secrets.

## 7. Observability

- Structured logs per request (request_id, skill_id, latency, cost)
- Daily cost rollup → cost dashboard (simple append-only log OK for MVP)

## 8. Security

- API keys in platform secrets only; never in repo
- Single-user token in `Authorization` header
- No PII storage

## 9. Open Questions (→ ADRs)

- ADR-001: LLM provider choice
- ADR-002: STT/TTS vendor(s)
- ADR-003: Deployment target
- ADR-004: Skill dispatch mechanism (keyword / embedding / LLM classifier)
- ADR-005: Client stack (web / desktop)

## 10. Revision History

| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | Lead Eng | Initial draft |
