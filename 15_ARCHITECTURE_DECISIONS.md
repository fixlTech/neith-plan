# Neith — Architecture Decisions

**Status:** Register established; no choices accepted through this draft

## Decision process
A proposal states context, hard constraints, at least two viable options, tradeoffs, affected contracts and migration path. Product/engineering/security owners review as relevant. Once accepted, update the canonical architecture and linked requirements; mark older decisions superseded with links. Implementation evidence may reveal a discrepancy but does not retroactively approve a choice.

## ADR template
- **ID/title/date/owner:**
- **Status:** Proposed, Accepted, Rejected, Superseded
- **Problem and constraints:** workload, user needs, compliance, existing code
- **Options:** benefits, costs, risks, reversibility
- **Decision and rationale:** why this option under stated assumptions
- **Consequences:** data model, APIs, UX, operations, security, migration
- **Validation:** prototype, benchmark, test, review date
- **Supersedes/links:**

## Decision queue
| ID | Question | Affected documents |
| --- | --- | --- |
| ADR-001 | Universal document representation and version model | 02, 07, 09, 11 |
| ADR-002 | Editing collaboration and conflict strategy | 06, 07, 09, 11 |
| ADR-003 | Image, motion, and shorts app boundaries | 03, 05, 08 |
| ADR-004 | Media preview/render pipeline and fidelity | 07, 08, 13, 14 |
| ADR-005 | Durable workflow orchestration and replay | 06, 08, 10 |
| ADR-006 | Authorization scopes and approval separation | 04, 06, 12 |
| ADR-007 | Storage, search, deployment topology | 09, 13, 14 |

The IDs reserve topics, not accepted outcomes.
