# System Understanding Architecture

**English** | [日本語](README.ja.md)

Reference architecture for integrating system understanding, documentation, source code, tests, and AI context in one Git repository.

## Purpose

This repository defines a practical documentation architecture whose primary goal is not merely to preserve specifications, but to help readers form an accurate mental model of a system quickly and then navigate to the exact implementation details they need.

The core idea is to keep conventional requirements, design documents, source code, database assets, tests, and infrastructure as authoritative artifacts while adding a thin **Understanding Layer** above them.

For AI-assisted development, AI agents use the same knowledge architecture but are treated as untrusted execution actors. Humans retain ownership of meaning, boundaries, invariants, risk acceptance, and approval; AI performs bounded exploration, implementation, checking, and evidence preparation.

## Information flow

```text
Understanding Layer
        ↓
Requirements / Design / Decisions
        ↓
Implementation / DB / Tests / Infrastructure
        ↓
Automated evidence / Human review
```

Navigation must also work in reverse: from code or data structures back to the business intent and decisions that explain why they exist.

## Repository structure

```text
.
├─ AGENTS.md                 # AI working agreement
├─ README.md
├─ README.ja.md
├─ docs/
│  ├─ understanding/
│  │  ├─ README.md
│  │  ├─ ja/                 # Japanese
│  │  ├─ system-overview.md
│  │  ├─ business-map.md
│  │  ├─ capability-map.md
│  │  ├─ architecture-map.md
│  │  ├─ invariants.md
│  │  ├─ change-guide.md
│  │  ├─ ai-development-policy.md
│  │  └─ glossary.md
│  ├─ requirements/
│  ├─ design/
│  ├─ decisions/
│  └─ templates/
├─ src/
├─ tests/
├─ db/
└─ infra/
```

Japanese documentation mirrors the English information architecture under `ja/` directories. Stable IDs, code identifiers, paths, and artifact responsibilities remain language-independent.

## Reading order

1. [System Overview](docs/understanding/system-overview.md)
2. [Business Map](docs/understanding/business-map.md)
3. [Capability Map](docs/understanding/capability-map.md)
4. [Architecture Map](docs/understanding/architecture-map.md)
5. [Invariants](docs/understanding/invariants.md)
6. [Change Guide](docs/understanding/change-guide.md)
7. Follow links into requirements, design, decisions, code, tests, DB, or infrastructure.

## Understanding design contract

Understanding documents should answer these six questions consistently:

1. **Purpose** — Why does this exist?
2. **Context** — Where does it sit in the wider system?
3. **Responsibility** — What is it responsible for, and what is it not responsible for?
4. **Flow** — What comes in, what happens, and what comes out?
5. **Dependencies** — What does it depend on or affect?
6. **Change Impact** — What must be checked when it changes?

## Traceability

Use stable IDs for meaningful boundaries and rules, for example:

- `CAP-BILLING`
- `BR-BILL-001`
- `REQ-BILL-001`
- `UC-BILL-001`
- `INV-BILL-001`
- `ADR-0001`

Do not annotate every method with IDs. Traceability should be maintained primarily at meaningful boundaries such as capabilities, rules, modules, APIs, batches, tables, and tests.

## Operating rules

- Documentation and related code changes should be reviewed in the same pull request.
- The Understanding Layer must remain concise and link to detailed authoritative artifacts rather than duplicate them.
- Every feature should have a discoverable path from business intent to code and tests.
- Review not only whether a change is correct, but whether a new reader can discover and understand it.
- Prefer Markdown and repository-native links so the repository remains portable and tool-independent.

## Localization policy

- Keep stable IDs, code identifiers, and repository paths language-independent.
- Keep translated documents semantically aligned rather than translating identifiers.
- Update affected translations in the same pull request when authoritative content changes.
- Add future languages using the same language-code directory convention.

## AI-assisted development

AI agents must start from the Understanding Layer rather than searching the entire repository blindly.

```text
README
  → System Overview
  → Business / Capability Map
  → Invariants
  → Relevant Requirements / ADRs
  → Design
  → Source / DB / Tests
```

Behavior-changing work should use a [Change Contract](docs/templates/change-contract-template.md). AI work ends in `HUMAN_REVIEW_REQUIRED` and should produce a [Human Review Request](docs/templates/human-review-request-template.md) ordered from business meaning to high-risk implementation details.

See [AI Development Policy](docs/understanding/ai-development-policy.md) and `AGENTS.md` for responsibility, evidence, least-privilege, stop, and approval rules.