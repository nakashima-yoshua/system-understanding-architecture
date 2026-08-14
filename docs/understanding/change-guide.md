# Change Guide

## Purpose

Provide a reverse index from a desired business or technical change to the documents, code, data, tests, and operational concerns that must be inspected.

## AI-assisted change flow

```text
Change request
  → Change Contract
  → Capability
  → Invariants
  → Requirements / ADRs
  → Design
  → Code / DB / Interfaces
  → Tests / automated checks
  → Human Review Request
  → Human approval
```

For AI-assisted work, define the allowed change boundary before implementation. AI must stop when material ambiguity, invariant conflict, scope expansion, or an unvalidated high-risk impact is discovered.

## Investigation sequence

For most changes, follow this order:

1. Identify the business activity in `business-map.md`.
2. Identify the owning capability in `capability-map.md`.
3. Identify applicable invariants in `invariants.md`.
4. Read related requirements and use cases.
5. Read relevant architecture decisions.
6. Inspect detailed design.
7. Inspect source code, database assets, interfaces, and tests.
8. Confirm operational, migration, validation, and rollback impact.

## Change index

| I want to change... | Start here | Then inspect | Typical validation |
|---|---|---|---|
| Business rule | Capability → Requirement → Invariant | Application logic, DB constraints, tests | Business scenario + invariant tests |
| Screen behavior | Business activity / Use case | UI design, API contract, application logic | UI + integration tests |
| Database schema | Capability / Data ownership | DB design, migrations, consumers | Migration + regression tests |
| External interface | Capability / Interface map | Contract, retries, error handling, consumers | Contract + failure tests |
| Batch behavior | Capability / Batch design | Schedule, inputs, outputs, idempotency | Re-run + failure recovery |
| Infrastructure | Architecture map | IaC, runtime dependencies, monitoring | Deployment + rollback |

## Per-change checklist

- What business outcome is changing?
- What remains unchanged?
- Which capability owns the change?
- Which invariants must remain true?
- Which requirement or decision explains the current behavior?
- Which code, data, interface, and test artifacts implement it?
- What downstream behavior can break?
- How will the change be verified and rolled back?
- Which claims are confirmed, inferred, unverified, or require a human decision?

Use `docs/templates/change-contract-template.md` before implementation and `docs/templates/human-review-request-template.md` before human approval.