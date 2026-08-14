# Architecture Map

## Purpose

Explain the major technical building blocks, dependency direction, runtime boundaries, and where detailed design can be found.

## Logical architecture

```text
Presentation / Interface
          ↓
Application
          ↓
Domain / Business Rules
          ↓
Infrastructure / Persistence / External Services
```

Adjust this diagram to the actual architecture. The important point is to communicate boundaries and dependency direction, not implementation detail.

## Component map

| Component | Responsibility | Depends on | Detail |
|---|---|---|---|
| Example component | Example responsibility | Example dependency | `docs/design/application/...` |

## Data ownership

| Data area | Owning component | Primary storage | Consumers |
|---|---|---|---|
| Example | Example component | Example DB | Example consumer |

## External interfaces

| Interface | Direction | Protocol | Detailed design |
|---|---|---|---|
| Example API | Inbound | HTTPS/JSON | `docs/design/interface/...` |

## Operational view

Document only the high-level runtime topology here. Deployment-specific detail belongs under `infra/` and related design documents.
