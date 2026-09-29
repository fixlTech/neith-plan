# Neith — End-to-End User Workflows

**Status:** Candidate flows; choose release scope and owners

## WF-01 Creator production
1. Sign in and choose organization/space; authorize project creation.
2. Create project with an explicit format/preset; upload or choose assets and observe processing.
3. Edit composition with undo/redo; autosave or explicitly save a version; indicate sync/conflict state.
4. Preview a chosen version; submit an export preset; inspect progress and download the artifact.
5. Reopen the project and verify element, timing, and asset reference fidelity.

Failure paths: invalid media, interrupted upload, expired session, autosave conflict, missing asset, unsupported schema, unavailable renderer, and quota exceeded. Each needs user-visible recovery and machine-readable error.

## WF-02 Team approval
An editor shares a version with scoped reviewers → reviewer comments against stable element/time references → editor creates revised version → reviewer compares, rejects or approves → publisher exports and delivers the approved version → audit records actors, versions, decisions, and artifact. Define timeout, delegation, self-approval, and post-approval edit invalidation.

## WF-03 Automated campaign
Verified external trigger → deduplicate by idempotency key → choose immutable template and data source versions → bind variables and assets → validate schema, permissions, licensing, and brand → pause for required approval → render variants from a snapshot → deliver to configured destinations → reconcile receipts → audit terminal outcome. Retry transient steps with bounded backoff; use compensation/manual repair for irreversible destinations. A resumed run must not silently rerender or republish a completed output.

## WF-04 Administration
Owner creates space, invites member with scoped role, changes policy, reviews access and audit, revokes member. A revoked principal must lose future access even if an editor tab remains open.

## Required specification per workflow
Trigger, actors, preconditions, state machine, source/version references, commands, events, permissions, limits, happy path, alternate/error paths, timeout, user messages, observability, and acceptance tests. Link each step to PRD IDs and service contracts before implementation.
