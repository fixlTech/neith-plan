# Neith — Product Requirements Document

**Version:** 0.2 draft · **Status:** Candidate requirements; no release scope approved

## 1. Scope and notation
This PRD defines behavior to evaluate, not a claim of completed functionality. `P0/P1/P2` mean candidate priority only. Every requirement must ultimately have an owner, persona, release, UX reference, permission, API contract, and test evidence. `MUST` below means required *if the capability is selected for a release*.

## 2. Primary scenarios
**S1 Creator output:** create a project, import assets, edit a composition, save, preview, export, and reopen it without losing supported edits. **S2 Team approval:** share a stable version, comment, revise, approve, and render only the eligible version. **S3 Automated campaign:** receive a verified trigger, bind approved template data, validate brand and permissions, pause for approval, render variants, deliver once, and audit each transition. Select the first shipping scenario after discovery.

## 3. Functional requirements
| ID | Candidate | Behavior and critical acceptance example |
| --- | --- | --- |
| N-001 | P0 Identity/tenancy | A user belongs to one or more organizations; a request cannot read another tenant's project by guessing its ID. |
| N-002 | P0 Projects | Create, rename, list, archive, and restore where policy permits; changes retain owner and timestamps. |
| N-003 | P0 Assets | Validate upload format/size; preserve original and checksum; expose processing status; fail safely on corrupt input. |
| N-004 | P0 Documents | Save an atomic version with schema version, asset references, and author; reopen with identical supported composition state. |
| N-005 | P0 Commands | Edits support undo/redo within defined history; failed save does not silently discard in-progress work. |
| N-006 | P0 Editor | Add, select, transform, order, and remove supported elements; selection and layout state remain distinct from document data. |
| N-007 | P0 Preview/export | Specify target preset, create an observable job, produce downloadable output or actionable failure; record source version and preset. |
| N-008 | P1 Image | Crop, transform, adjust, and layer supported raster assets while preserving original inputs. |
| N-009 | P1 Video/motion | Place clips on a timeline, trim, control timing, preview, and export with declared frame/timebase behavior. |
| N-010 | P1 Audio | Arrange tracks, adjust gain and synchronization, preview, and export with declared sample-rate behavior. |
| N-011 | P1 Templates | Instantiate an approved version with typed variables; reject missing or invalid required bindings. |
| N-012 | P1 Brand | Validate selected rules at creation/export; show rule, affected element, severity, and permitted override actor. |
| N-013 | P1 Collaboration | Share by scope; anchor comments to document version and location/time; preserve attribution. |
| N-014 | P1 Approval | Review a frozen version; define rejection/resubmission and invalidation after edits; prevent self-approval where policy forbids it. |
| N-015 | P1 Workflow | Persist state and idempotency key; retry transient failures, pause/resume approval, and surface terminal errors. |
| N-016 | P1 Delivery | Record destination and artifact version; prevent duplicate publication on retried requests where supported. |
| N-017 | P1 Audit | Capture actor, tenant, action, time, correlation, before/after references, and outcome for privileged and production actions. |
| N-018 | P2 Advanced production | Multi-format variants, bulk operations, complex effects, integrations, and analytics require separate specifications. |

## 4. Business rules to approve
An archived project is read-only except restore/delete operations; source assets remain immutable; output records reference a specific document/template/brand version; authorization is checked when an action executes, not only when the UI loads; approval applies to a defined version and policy snapshot; render and delivery retries must distinguish safe replay from a new request. Retention, quotas, licensing, and billing are open decisions.

## 5. Edge cases and expected behavior
Interrupted upload: recover or show explicit failure without a phantom asset. Lost connection during edit: preserve local state and explain sync status. Concurrent edit: apply a defined merge/conflict policy, never silently overwrite. Missing/deleted asset: show a resolvable reference error. Unsupported schema: preserve bytes and require migration/compatible client. Revoked permission: stop subsequent mutations. Duplicate trigger: resolve to the existing workflow run. Render crash: retry within policy and keep artifact lineage. Approval timeout: enter an explicit expired/escalated state.

## 6. Acceptance and traceability
A selected requirement is ready for implementation only when example-based criteria cover success, denial, invalid input, concurrent/retry behavior, observability, and accessibility. Link each to `06_USER_WORKFLOWS.md`, `03_PLATFORM_MODULE_INVENTORY.md`, an API/event contract, and tests in `18_TESTING_AND_QUALITY.md`. No acceptance criterion is satisfied by a UI mockup alone.

## 7. Open decisions
Choose first persona/workflow, platform support, exact media formats, collaboration depth, import/export fidelity, approval policy, hosting/data residency, and performance budgets. See `91_OPEN_QUESTIONS.md`.
