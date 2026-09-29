# Neith — Service Boundaries and Ownership

**Status:** Logical ownership proposal; not a microservice deployment decision

| Domain | Exclusive write authority | Read/API and events to define | Must not own |
| --- | --- | --- | --- |
| Identity/tenant | Membership and grants | Auth context, membership changes | Document content |
| Project/core | Projects, document versions, commands | Save/load/version events | Raw media bytes |
| Assets | Media metadata, variants, rights | Upload/resolve/search; asset ready | Project approval |
| Template/brand | Template versions, rule sets | Instantiate/validate; version published | Render job state |
| Collaboration | Presence, comments, sessions | Subscribe/comment; comment changes | Canonical document versions |
| Review | Requests, decisions, approval state | Approve/reject; review state | Editing reviewed snapshot |
| Workflow | Durable runs, step state, idempotency | Start/resume/cancel; step events | Renderer internals |
| Render | Queued jobs, presets, artifacts | Submit/status/cancel; artifact ready | Delivery receipts |
| Delivery | Destinations, publish attempts/receipts | Publish/status; delivery result | Document editing |
| Audit/operations | Activity evidence, policy administration | Query/export; retention controls | Rewriting domain history |

## Ownership contract
Every domain defines stable IDs, source of truth, schema and migrations, authorized mutations, API/event versions, ordering guarantees, SLO, retention, and recovery. Cross-domain data are referenced by IDs and immutable versions where needed; avoid shared-table writes. A read model may duplicate data with stated staleness.

## Transaction examples
Saving a document version and emitting `document.version.created` must be durable together. An approval stores the document version and policy context; a render request captures that approval reference. Workflow retries query job/delivery state before repeating a side effect. Unknown outcomes are reconciled, not blindly retried.

## Deployment choice
Start with these boundaries in modules if that reduces operational complexity. Split a domain into an independent service only for a measured scale, isolation, ownership, or release need. Record actual deployables separately from this conceptual map.
