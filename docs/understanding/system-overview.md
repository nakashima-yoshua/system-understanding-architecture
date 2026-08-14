# System Overview

## Purpose

Describe the system in enough detail for a new reader to understand its purpose, scope, users, external boundaries, and principal data flows in approximately 5–10 minutes.

## Business purpose

> Replace this section with the business outcome the system exists to produce.

## Primary users and actors

| Actor | Goal | Main interaction |
|---|---|---|
| Example business user | Complete a business process | Web / desktop UI |
| External system | Exchange data | API / file / message |
| Operator | Maintain service health | Monitoring / administration |

## System boundary

### In scope

- Core business responsibilities owned by this system.

### Out of scope

- Responsibilities explicitly owned elsewhere.

## Major capabilities

See [Capability Map](capability-map.md).

## High-level flow

```text
User / External System
        ↓
Interface
        ↓
Application / Business Logic
        ↓
Persistence / External Integration
```

## External dependencies

| Dependency | Purpose | Failure impact |
|---|---|---|
| Example external API | Data exchange | Relevant function becomes unavailable |

## Where to go next

- Business perspective: [Business Map](business-map.md)
- Technical structure: [Architecture Map](architecture-map.md)
- Change investigation: [Change Guide](change-guide.md)
