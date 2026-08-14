# AI Development Policy

## Purpose

Define responsibility, authority, verification, and review boundaries for AI-assisted development. AI agents are treated as untrusted execution actors: useful for producing work, but their claims are not accepted without evidence and human judgment where required.

## Responsibility model

### Human owns
- business purpose and priority;
- capability boundaries and responsibility;
- business rules and invariants;
- architecture boundaries, dependency direction, and data ownership;
- acceptance criteria and risk acceptance;
- approval, release, rollback, and production decisions.

### AI may perform
- repository exploration and impact analysis;
- clarification questions and alternative proposals;
- implementation within an approved change contract;
- test and documentation changes;
- evidence collection and review report preparation.

### Automated verification owns objective checks
- build and test execution;
- lint, type, static, dependency, and secret checks;
- schema, migration, link, traceability, and policy checks where configured.

Passing automation is evidence, not proof of total correctness.

## Evidence classes

- `CONFIRMED` — directly observed from repository content, diffs, commands, tests, or tool output.
- `INFERRED` — conclusion derived from confirmed information.
- `UNVERIFIED` — not checked or not practically checkable in the current environment.
- `HUMAN_DECISION` — requires human business, architecture, operational, or risk judgment.

AI confidence is not evidence.

## Risk levels

| Level | Typical change | Required control |
|---|---|---|
| LOW | docs, lint, mechanical non-behavioral change | AI work → automated checks → human lightweight review |
| MEDIUM | feature or bug fix inside an existing capability | human-approved contract → AI work → checks → human review |
| HIGH | business rule, boundary, data, interface, security-sensitive change | human design approval → AI work → independent review/checks → focused human code review |
| CRITICAL | auth, billing/accounting, personal data, destructive operations, irreversible migration, production-critical contract | human-led; AI limited to analysis and controlled implementation assistance |

## Human review order

Review from meaning to implementation, not from code upward:

1. change purpose and out of scope;
2. business rules and invariants;
3. data, external contracts, and side effects;
4. migration, failure, and recovery;
5. test and automated-check evidence;
6. high-risk code;
7. unresolved items and residual risk;
8. approval decision.

## State model

```text
ANALYZING
  ↓
PLAN_REVIEW_REQUIRED   # when risk or ambiguity requires it
  ↓
IMPLEMENTING
  ↓
SELF_CHECK_COMPLETED
  ↓
HUMAN_REVIEW_REQUIRED
  ├─ APPROVED
  ├─ CHANGES_REQUESTED → IMPLEMENTING
  └─ REJECTED / POSTPONED
```

Only a human reviewer can create an approval decision. AI must not claim `DONE`, `MERGEABLE`, or `RELEASE_READY` when human approval is still required.

## Least privilege

AI access should be limited to the minimum repository, environment, network, secret, and command permissions needed for the task. Production data mutation, protected-branch merge, and production deployment require separate human-controlled authorization.