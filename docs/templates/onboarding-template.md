# ONBOARDING.md template for an adopting project

Replace every placeholder with an authoritative reference; do not claim unfinished steps are complete.

## Project orientation
- Business goal and users: TODO
- System overview, capability/architecture maps, invariants: TODO

## Contacts and authorization
- Onboarding owner / reviewer: TODO
- Least-privilege access request: TODO
- Approved test environment and permitted commands: TODO
- Prohibited operations, production escalation: TODO

## Setup and first smoke test
- Baseline branch / Git SHA: TODO
- Setup prerequisites and repeatable launch/smoke commands: TODO
- Result: NOT_RUN (or record PASS / FAIL / BLOCKED with evidence)

## Representative feature
- Business scenario and expected outcome: TODO
- Entry → source → SQL/DB → interfaces → test references: TODO
- Sources, confirmed facts and unknowns: TODO

## First safe task
- Approved issue, change boundary, exclusions and tests: TODO
- Review-ready PR link: NOT_RUN

## Operational rehearsal
- Runbook, observability and recovery contact: TODO
- Read-only or isolated exercise: NOT_RUN

## Acceptance
Explain system context; independently reproduce approved checks; trace one feature with evidence; submit a small PR for review; locate the safe incident escalation path. Do not treat an exercise as authority to merge, deploy or change production.

Reference: [onboarding guide](../onboarding/README.md).
