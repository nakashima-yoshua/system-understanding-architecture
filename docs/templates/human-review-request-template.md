# Human Review Request

- Review request ID: `HRR-YYYY-NNNN`
- Change: `CHANGE-...`
- Review type: plan | final | re-review
- Status: `HUMAN_REVIEW_REQUIRED`
- Risk: LOW | MEDIUM | HIGH | CRITICAL
- Capability: `CAP-...`
- PR / commit: ...

Use `CONFIRMED`, `INFERRED`, `UNVERIFIED`, and `HUMAN_DECISION` for material claims.

## 0. Decision requested
- What the human must decide:
- Scope being approved:
- Scope not being approved:
- AI work currently stopped at:
- Next step after approval:

## 1. Purpose and out of scope
- Purpose:
- Expected outcome:
- In scope:
- Out of scope:
- Scope deviation detected: yes / no

Human checks: Is this the right change, and only the right change?

## 2. Business rules and invariants
| Item | Before | After / preservation | Evidence class | Evidence |
|---|---|---|---|---|
| `BR-...` / `INV-...` | | | | |

Human checks: Are the business meaning, forbidden states, exceptions, and invariants correct?

## 3. Data, external contracts, and side effects
- Data changed:
- External contracts changed:
- Persistence / transactions:
- External sends / notifications:
- Auth / personal / secret data impact:
- Cross-capability impact:

Human checks: Are ownership, compatibility, idempotency, ordering, and sensitive-data effects acceptable?

## 4. Migration, failure, and recovery
- Apply sequence:
- Compatibility during migration:
- Expected failure modes:
- Detection:
- Rollback:
- Data correction:
- Irreversible effects:

Human checks: Can failure be detected and realistically recovered?

## 5. Test and automated-check evidence
| Acceptance criterion / check | Result | Evidence | Coverage limits |
|---|---|---|---|
| | PASS / FAIL / NOT RUN | | |

- Checks not run and why:
- Environment differences:
- Tests written from the same assumptions as implementation:

Human checks: Does the evidence validate business expectations rather than merely mirror the implementation?

## 6. High-risk code
| Priority | File / location | Why changed | Risk | Human review point |
|---|---|---|---|---|
| | | | | |

Prioritize business rules, transactions, auth, destructive data operations, external effects, concurrency, retries/idempotency, error handling, migrations, and irreversible behavior.

## 7. Unresolved items and residual risk
| Priority | Item | Status | Impact | Required owner |
|---|---|---|---|---|
| | | | | |

### AI assumptions
| Assumption | Basis | Impact if wrong |
|---|---|---|
| | | |

## 8. Human decision
- [ ] APPROVED
- [ ] CONDITIONALLY APPROVED
- [ ] CHANGES REQUESTED
- [ ] REJECTED
- [ ] POSTPONED

Conditions / comments:

AI must not treat this change as approved, mergeable, or release-ready until a human explicitly makes the decision.