# User Stories / Requirements — Kotoba

Format: `As a <user>, I want <capability>, so that <benefit>.` INVEST criteria. Acceptance criteria in Given/When/Then.

Source of user voice: Customer role = Browser Claude. Prioritization: TPM/PO = Kosuke (MoSCoW).

## MVP (Must)

### US-001 — Push-to-talk query
**As** a user, **I want** to press a key and speak a question, **so that** I get an answer without typing.
- Priority: M
- Given the app is running, When I press and hold the PTT key and speak, Then my speech is transcribed and sent within 1s of key release.
- Acceptance: EN + JA both transcribed.

### US-002 — Spoken reply with on-screen detail
**As** a user, **I want** a short spoken reply plus detailed info on screen, **so that** I can glance for depth without re-listening.
- Priority: M
- Given a completed query, When the assistant replies, Then TTS plays ≤ 30s summary AND the detail panel shows structured data consistent with the summary.
- Acceptance: no contradiction between spoken and displayed content (verified on a 10-case test).

### US-003 — Skill invocation
**As** a user, **I want** the assistant to call the right skill for my request, **so that** I get real data instead of hallucinated answers.
- Priority: M
- Given a query that matches a known skill, When processed, Then the skill is invoked and its result is used to generate the reply.
- Acceptance: ≥ 90% correct skill selection on 60-case dispatcher test.

### US-004 — Graceful fallback
**As** a user, **I want** a useful answer even when no skill matches, **so that** the assistant still feels helpful.
- Priority: M
- Given a query with no matching skill, Then the LLM answers directly and the detail panel shows "general response" mode.

### US-005 — Cloud availability
**As** a user, **I want** to reach the assistant from a second machine, **so that** it behaves like a service, not a script.
- Priority: M
- Given the backend is deployed, When I open the client on another machine with my token, Then I can complete a full query loop.

## Should

### US-006 — Cost visibility
**As** the operator, **I want** daily API cost logged, **so that** I can enforce the $60/mo cap.
- Priority: S
- Given a day of usage, Then the cost log shows per-skill and total USD spend.

### US-007 — Error transparency
**As** a user, **I want** the UI to show when a skill fails, **so that** I don't think the assistant is lying.
- Priority: S

## Could

- US-008 Conversation continuity within session (stateful pronouns)
- US-009 Voice interrupt (barge-in)
- US-010 Theme / visual polish

## Won't (this release)

- Wake word
- Multi-user
- Mobile app
- Cross-session memory
