# Understanding Layer

This directory is the primary entry point for human and AI readers.

Its purpose is to create a correct mental model quickly and route the reader to authoritative detail. It should not duplicate detailed requirements or design specifications.

## Documents

- `system-overview.md` — purpose, actors, boundaries, major flows
- `business-map.md` — business-oriented navigation
- `capability-map.md` — bridge between business capabilities and implementation
- `architecture-map.md` — high-level technical structure and dependency direction
- `invariants.md` — conditions changes must not violate
- `change-guide.md` — reverse lookup from desired change to affected knowledge and code
- `ai-development-policy.md` — responsibility, trust, evidence, and human-review rules for AI-assisted development
- `glossary.md` — canonical terminology

## Rule

If a reader must inspect implementation details before understanding what the system does and where a concern belongs, this layer is incomplete.

AI agents use the same knowledge architecture, but are not trusted to approve their own conclusions or changes. Their work must stay within an approved scope, produce verifiable evidence, and end in human review when required.