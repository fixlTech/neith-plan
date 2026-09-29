# Product requirements (PRD)

Status: Draft framework; requirements are candidates

## Requirement format
For each requirement record ID, persona, trigger, preconditions, main flow, failure/edge flows, data, permissions, measurable acceptance criteria, priority, dependency, and evidence/status.

## Candidate capabilities
| ID | Capability | Initial acceptance question |
| --- | --- | --- |
| P-001 | Organization and project setup | Can a user create a scoped working area and assign access? |
| P-002 | Asset ingestion | Are supported media validated, indexed, versioned, and traceable? |
| P-003 | Unified composition | Can supported media be combined and reopened without data loss? |
| P-004 | Image editing | Can changes be reversed and exported predictably? |
| P-005 | Video and timeline | Can a user edit tracks, preview, and export reliably? |
| P-006 | Audio mixing | Are tracks, gain, timing, and exports coherent with video? |
| P-007 | Templates and brand | Can a template be safely populated and checked against rules? |
| P-008 | Collaboration and review | Can comments and approvals refer to stable versions? |
| P-009 | Rendering and delivery | Are jobs observable, retryable, and reproducible? |
| P-010 | Automation | Can authorized workflows execute with audit and human gates? |

## Cross-cutting requirements
Permission checks on every mutation; tenant isolation; accessibility; localization plan; autosave and recovery; import/export fidelity; error handling; billing/entitlement rules if commercialized.

## Acceptance gate
Do not call this PRD complete until each candidate is split into testable requirements with edge cases, owners, priorities, and approved release scope. See workflows in `06_USER_WORKFLOWS.md`.
