# Onboarding a new project contributor

This repository is a **reference architecture**, not the actual target system. An adopting project should link from its own `ONBOARDING.md` to this guide, while owning its real setup instructions, access rules, Runbooks and approvals. Assess ability to work safely, not pages read.

## Host preparation

Name one representative business feature, a baseline Git revision, an approved development or test environment, a safe first task, a mentor/contact, escalation conditions, existing smoke-test commands and permitted operations. Do not place credentials in onboarding files.

## Guided progression

| Step | Task | Observable exit criterion |
| --- | --- | --- |
| 1. Orientation | Read system overview, business/capability/architecture maps, invariants and change guide | Explain purpose, boundaries and essential invariants |
| 2. Environment | Follow the adopting project's instructions to clone, build, launch and run a smoke test | Record exact command, revision, result and blockers |
| 3. One feature | Trace a business scenario from entry through source, SQL/data changes, external effects and tests; use FMW `catchup` if available | Explain the path with evidence and known unknowns |
| 4. First bounded task | Add one agreed test or small safe change | Produce relevant test results and a review-ready PR, not a merge |
| 5. Operations | Use an approved Runbook to rehearse investigation/recovery in a nonproduction environment, or conduct a read-only walkthrough | Explain escalation, rollback decision and prohibited actions |

A first day to two weeks is illustrative only; mark unavailable setup `BLOCKED` and unexecuted checks `NOT_RUN`. Never infer production authorization from passing an exercise.

## Continuous improvement

Link to authoritative source, test records and feature knowledge rather than duplicating them. Record uncertain claims as unverified, and contribute fixes to stale onboarding steps. For a project-specific starting page use the [template](../templates/onboarding-template.md); see [repository relationships](../repository-relationships.md) for tool responsibilities.
