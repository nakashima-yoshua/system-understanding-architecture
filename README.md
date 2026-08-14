# System Understanding Architecture

Reference architecture for integrating system understanding, documentation, source code, tests, and AI context in one Git repository.

## Purpose

This repository defines a practical documentation architecture whose primary goal is not merely to preserve specifications, but to help readers form an accurate mental model of a system quickly and then navigate to the exact implementation details they need.

The core idea is to keep conventional requirements, design documents, source code, database assets, tests, and infrastructure as authoritative artifacts while adding a thin **Understanding Layer** above them.

## Information flow

```text
Understanding Layer
        ↓
Requirements / Design / Decisions
        ↓
Implementation / DB / Tests / Infrastructure
```

Navigation must also work in reverse: from code or data structures back to the business intent and decisions that explain why they exist.

## Repository structure

```text
.
├─ README.md
├─ docs/
│  ├─ understanding/
│  │  ├─ README.md
│  │  ├─ system-overview.md
│  │  ├─ business-map.md
│  │  ├─ capability-map.md
│  │  ├─ architecture-map.md
│  │  ├─ change-guide.md
│  │  └─ glossary.md
│  ├─ requirements/
│  │  ├─ README.md
│  │  ├─ business/
│  │  ├─ usecases/
│  │  └─ functional/
│  ├─ design/
│  │  ├─ README.md
│  │  ├─ application/
│  │  ├─ database/
│  │  ├─ interface/
│  │  └─ batch/
│  ├─ decisions/
│  └─ templates/
├─ src/
├─ tests/
├─ db/
└─ infra/
```

## Reading order

1. [System Overview](docs/understanding/system-overview.md)
2. [Business Map](docs/understanding/business-map.md)
3. [Capability Map](docs/understanding/capability-map.md)
4. [Architecture Map](docs/understanding/architecture-map.md)
5. [Change Guide](docs/understanding/change-guide.md)
6. Follow links into requirements, design, decisions, code, tests, DB, or infrastructure.

## Understanding design contract

Understanding documents should answer these six questions consistently:

1. **Purpose** — Why does this exist?
2. **Context** — Where does it sit in the wider system?
3. **Responsibility** — What is it responsible for, and what is it not responsible for?
4. **Flow** — What comes in, what happens, and what comes out?
5. **Dependencies** — What does it depend on or affect?
6. **Change Impact** — What must be checked when it changes?

## Traceability

Use stable IDs for business capabilities, requirements, use cases, and architecture decisions, for example:

- `CAP-BILLING`
- `REQ-BILL-001`
- `UC-BILL-001`
- `ADR-0001`

Do not annotate every method with IDs. Traceability should be maintained primarily at meaningful boundaries such as capabilities, modules, APIs, batches, tables, and tests.

## Operating rules

- Documentation and related code changes should be reviewed in the same pull request.
- The Understanding Layer must remain concise and link to detailed authoritative artifacts rather than duplicate them.
- Every feature should have a discoverable path from business intent to code and tests.
- Review not only whether a change is correct, but whether a new reader can discover and understand it.
- Prefer Markdown and repository-native links so the repository remains portable and tool-independent.

## AI usage

AI agents should start from the Understanding Layer rather than searching the entire repository blindly. The recommended exploration path is:

```text
README
  → System Overview
  → Business / Capability Map
  → Relevant Requirement / Decision
  → Design
  → Source / DB / Tests
```

This makes the same knowledge architecture useful to both humans and AI.
