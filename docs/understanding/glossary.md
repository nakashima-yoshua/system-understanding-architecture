# Glossary

Use this file as the canonical vocabulary for business and technical concepts that are easily confused or have system-specific meanings.

| Term | Meaning | Avoid / Notes |
|---|---|---|
| Capability | A stable ability to provide a business outcome, connecting business intent to implementation | Not an individual screen, method, or module |
| Invariant | A condition that must remain true across permitted changes | Not a synonym for every requirement |
| Understanding Layer | Navigation and mental-model layer above detailed specifications | Must not duplicate detailed design |
| ADR | Architecture Decision Record | Records significant decisions and rationale |
| Change Contract | Explicit boundary, acceptance criteria, invariants, permissions, and stop conditions for a change | AI must not silently expand it |
| Evidence | Objective result used to support a claim, such as a diff, test, command, or check | AI confidence is not evidence |
| Human Review | Human judgment over meaning, risk, evidence, and approval | AI review does not replace approval |
| AI Agent | Untrusted execution actor operating with bounded authority | May propose and implement; may not self-approve |

Add project-specific terms as soon as ambiguity appears in requirements, design, code, or user conversations.