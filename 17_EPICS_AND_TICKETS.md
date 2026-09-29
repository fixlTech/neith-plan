# Neith — Epics and Implementation Tickets

**Status:** Backlog structure and candidate epics; not ready-to-build Jira tickets

| Epic | Outcome | Required predecessor | Representative vertical slice |
| --- | --- | --- | --- |
| E01 Discovery/audit | Verified baseline and prioritized workflow | Source access | Trace a real project from UI to persisted data |
| E02 Identity/tenancy | Safe scoped project access | Policy ADR | Invite user and deny cross-tenant read |
| E03 Core/versioning | Reopenable composition | Document ADR | Edit, save, reload, undo |
| E04 Assets | Usable media with lineage | Storage rules | Upload, process, place, recover failure |
| E05 First editor | Selected creation task | E03/E04 | Produce a real artifact |
| E06 Rendering | Reproducible output | Version snapshot | Queue, preview, export, retry |
| E07 Team review | Version-bound decision | E02/E03 | Comment, revise, approve |
| E08 Brand/templates | Reuse with validation | E04/E07 | Bind and validate branded output |
| E09 Automation/delivery | Recoverable production | E06/E08 | Trigger to audited delivery |
| E10 Enterprise quality | Governed reliable operation | Defined NFRs | Isolation, load, recovery, accessibility |

## Ticket template
Title and stable ID; user/business outcome; PRD/workflow IDs; owner; current-state evidence; scope and explicit exclusions; dependencies; design/API/schema references; acceptance examples including denial/error/retry; telemetry; test strategy; rollout/rollback; definition of done.

## Refinement gate
A ticket is ready only when dependencies are settled, data ownership and permissions are clear, UX/error states exist, and acceptance can be demonstrated. Split broad epics into reviewable vertical slices; link implementation PRs and evidence back to IDs.
