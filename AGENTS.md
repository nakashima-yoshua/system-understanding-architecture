# AI Agent Working Agreement

This repository treats AI agents as untrusted execution actors. AI may explore, propose, implement, test, and summarize changes, but must not self-approve them.

## Required reading order

1. `README.md`
2. `docs/understanding/system-overview.md`
3. `docs/understanding/business-map.md`
4. `docs/understanding/capability-map.md`
5. `docs/understanding/invariants.md`
6. Relevant requirements, ADRs, and design documents
7. Source, database, tests, and infrastructure

Use the corresponding `ja/` documents when working in Japanese. Stable IDs and responsibilities must remain aligned across languages.

## Operating rules

- Work from an explicit change contract when changing behavior.
- Prefer the smallest change that satisfies the approved scope.
- Preserve existing architecture, dependency direction, data ownership, and naming unless the change contract explicitly authorizes a change.
- Do not invent requirements or silently resolve contradictory sources.
- Keep documentation, code, tests, DB assets, and interface changes synchronized in the same pull request when they are affected.
- Distinguish facts from inference. Report `CONFIRMED`, `INFERRED`, `UNVERIFIED`, and `HUMAN_DECISION` separately.
- AI self-checks are evidence preparation, not approval.

## Stop and request human review when

- requirements have multiple material interpretations;
- authoritative artifacts conflict;
- the requested work exceeds the approved scope;
- an invariant cannot be preserved;
- the change affects authentication, authorization, billing, accounting, personal data, destructive data operations, data ownership, or public contracts;
- a destructive or irreversible migration is required;
- validation or rollback cannot be defined with reasonable confidence.

## Prohibited actions

Unless a human explicitly authorizes them through a controlled workflow, AI must not:

- mark its own change `APPROVED`, `MERGEABLE`, `RELEASE_READY`, or equivalent;
- merge to a protected branch;
- deploy to production;
- modify production data;
- access or expose secrets beyond the minimum tool permission required;
- expand network, repository, or environment permissions;
- introduce unrelated refactoring or dependencies;
- run destructive commands outside an explicitly approved and isolated environment.

## Completion state

AI completion means:

```text
SELF_CHECK_COMPLETED
        ↓
HUMAN_REVIEW_REQUIRED
```

The final AI report must follow `docs/templates/human-review-request-template.md` or its Japanese counterpart. Human approval is a separate action performed by a human reviewer.