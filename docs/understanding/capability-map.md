# Capability Map

## Purpose

Bridge business intent and implementation. A capability is the preferred traceability unit because it is stable enough for business discussion and concrete enough to map to requirements, modules, data, interfaces, and tests.

## Capability template

### `CAP-EXAMPLE` — Example Capability

**Purpose**  
What business outcome this capability provides.

**Context**  
Where it sits in the larger business process.

**Responsibilities**
- What this capability owns.
- What it explicitly does not own.

**Flow**
```text
Input → Processing → Output
```

**Related artifacts**

| Type | Link / ID |
|---|---|
| Requirements | `REQ-EXAMPLE-001` |
| Use cases | `UC-EXAMPLE-001` |
| Decisions | `ADR-0001` |
| Application | `src/...` |
| Database | `db/...` |
| Interfaces | `docs/design/interface/...` |
| Tests | `tests/...` |

**Dependencies**  
List upstream and downstream dependencies.

**Change impact**  
List the main areas that must be checked when this capability changes.

## Index

| Capability ID | Name | Business process | Main implementation |
|---|---|---|---|
| `CAP-EXAMPLE` | Example Capability | Example Process | `src/...` |
