# Change Guide

## Purpose

Provide a reverse index from a desired business or technical change to the documents, code, data, tests, and operational concerns that must be inspected.

## Investigation sequence

For most changes, follow this order:

1. Identify the business activity in `business-map.md`.
2. Identify the owning capability in `capability-map.md`.
3. Read related requirements and use cases.
4. Read relevant architecture decisions.
5. Inspect detailed design.
6. Inspect source code, database assets, interfaces, and tests.
7. Confirm operational and migration impact.

## Change index

| I want to change... | Start here | Then inspect | Typical validation |
|---|---|---|---|
| Business rule | Capability → Requirement | Application logic, DB constraints, tests | Business scenario tests |
| Screen behavior | Business activity / Use case | UI design, API contract, application logic | UI + integration tests |
| Database schema | Capability / Data ownership | DB design, migrations, consumers | Migration + regression tests |
| External interface | Capability / Interface map | Contract, retries, error handling, consumers | Contract + failure tests |
| Batch behavior | Capability / Batch design | Schedule, inputs, outputs, idempotency | Re-run + failure recovery |
| Infrastructure | Architecture map | IaC, runtime dependencies, monitoring | Deployment + rollback |

## Per-change checklist

- What business outcome is changing?
- What remains unchanged?
- Which capability owns the change?
- Which requirement or decision explains the current behavior?
- Which code, data, interface, and test artifacts implement it?
- What downstream behavior can break?
- How will the change be verified and rolled back?
