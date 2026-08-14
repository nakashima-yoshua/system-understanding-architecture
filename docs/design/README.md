# Design

Detailed design artifacts live here. This layer explains how requirements are realized technically.

## Structure

- `application/` — modules, services, domain/application behavior
- `database/` — schema, ownership, constraints, migrations
- `interface/` — APIs, files, messages, integration contracts
- `batch/` — batch jobs, scheduling, idempotency, recovery

Design documents should link upward to capabilities/requirements and downward to code/tests.
