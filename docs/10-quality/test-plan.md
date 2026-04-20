# Quality Management / Test Plan — Kotoba

**Owner:** QA (Antigravity IDE)
**Related:** User Stories, TDD §4–5, Defect Log

## 1. Quality Objectives

| ID | Objective | Metric | Target |
|----|---|---|---|
| Q1 | Correct skill dispatch | % correct on 60-case test set | ≥ 90% |
| Q2 | Per-skill correctness | % pass on 20-case set per skill | ≥ 90% |
| Q3 | Voice/UI consistency | Contradiction rate on 10-case audit | 0% |
| Q4 | Latency | Voice-in → voice-out start (LLM-only path) | ≤ 5s p50 |
| Q5 | Cost envelope | Daily spend | ≤ $2/day (avg) |
| Q6 | Code health | Unit test coverage on orchestrator + skills | ≥ 70% |

## 2. Test Levels

| Level | Owner | Scope |
|---|---|---|
| Unit | Dev (Codex) | Pure functions, skill logic, contract validators |
| Integration | QA (Antigravity) | API endpoints end-to-end with mocked vendors |
| Contract | QA (Antigravity) | `Response` contract: summary derivable from detail |
| System | QA (Antigravity) | Full voice loop + browser-automated UI checks against live (cheap) vendors |
| UAT | Customer (Browser Claude) | Scenario-based, per User Story |

## 3. Test Data

- 60-case dispatcher set: 20 clearly-skill-A, 20 clearly-skill-B, 20 no-skill (fallback expected)
- 20-case × 3 skills = 60 functional cases
- 10-case voice/UI audit set (hand-picked edge cases)
- EN + JA coverage in each set (50/50)

## 4. Entry / Exit Criteria per Sprint

**Entry:** Sprint Plan merged; test set for sprint's deliverables drafted.
**Exit:** All in-sprint stories have passing tests; defects logged; Status Report written.

## 5. Defect Management

Defects go to `docs/10-quality/defect-log.md`. Severity: S1 (blocker) / S2 (major) / S3 (minor) / S4 (cosmetic). S1/S2 must be closed before Sprint Review.

## 6. UAT Procedure

1. Customer (Browser Claude) runs through each MVP User Story.
2. Each story gets Pass / Fail / Pass-with-notes.
3. Failures → defect log + Change Request if scope-related.
4. UAT report goes to `docs/11-closing/` and blocks Closing until signed off.

## 7. Independence

QA (Antigravity) does not write production code. Dev (Codex) does not sign off tests. This separation is a program invariant.
