# Invariants

## Purpose

Record conditions that changes must not violate. Invariants are intentionally smaller and stricter than general requirements: they define states or behaviors that must remain true across implementations.

Use stable IDs such as `INV-BILL-001` when an invariant needs traceability.

## Template

### `INV-EXAMPLE-001` — Short name

**Invariant**  
State the condition that must always hold.

**Why it matters**  
Explain the business, security, consistency, or operational consequence of violating it.

**Applies to**
- Capability: `CAP-...`
- Requirement: `REQ-...`
- Data / interface / module: ...

**Verification**
- Automated test: `tests/...`
- Static / schema / policy check: ...
- Human review point: ...

**Allowed exceptions**  
List only explicitly approved exceptions. If none, write `None`.

## Rules

- Do not duplicate ordinary functional requirements here.
- Prefer invariants that can be verified by tests, constraints, static checks, or explicit human review.
- A change contract must identify affected invariants.
- If an AI agent cannot preserve an applicable invariant, it must stop and request human review.