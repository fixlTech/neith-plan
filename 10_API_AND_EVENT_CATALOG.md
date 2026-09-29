# Neith — API and Event Catalogue

**Status:** Proposed contract inventory; routes and payload schemas require review

## API groups
| Group | Candidate operations | Owner | Permission examples |
| --- | --- | --- | --- |
| Identity/organizations | Session, membership, invite, revoke | Identity | `membership.manage` |
| Spaces/projects | Create/list/read/archive/restore | Project | `project.create`, `project.read` |
| Documents | Load, apply command, save version, compare | Core | `document.edit`, `document.read` |
| Assets | Create upload, finalize, resolve, search | Assets | `asset.upload`, `asset.read` |
| Templates/brand | Publish version, bind, validate | Template/brand | `template.publish`, `brand.read` |
| Review | Request, comment, decide | Review | `review.request`, `review.approve` |
| Workflows | Start, pause/resume, cancel, inspect | Workflow | `workflow.run` |
| Render/delivery | Submit, status, artifact, publish | Render/delivery | `render.submit`, `delivery.publish` |
| Audit/admin | Query evidence, set policy | Enterprise | `audit.read`, `policy.manage` |

## Required API specification
For each operation define stable ID, protocol and path, authentication, tenant/scope, request and response schema, version, idempotency, pagination/filtering, rate limits, validation errors, conflict behavior, audit action, and examples. Long-running requests return a job/run ID; polling or subscription exposes state. Use opaque resource IDs and verify tenancy on lookup.

## Event envelope candidate
`event_id`, `event_type`, `schema_version`, `occurred_at`, `tenant_id`, `aggregate_type`, `aggregate_id`, `aggregate_version`, `correlation_id`, `causation_id`, `actor_type`, `actor_id`, `idempotency_key`, `trace_id`, `payload`, `before_ref`, `after_ref`. Include only data subscribers need; classify/redact sensitive fields.

## Candidate events
`asset.ready`, `document.version.created`, `review.requested`, `review.approved`, `workflow.started`, `workflow.step.failed`, `render.completed`, `delivery.completed`. Producers publish committed facts; consumers are idempotent. Define ordering per aggregate, replay/retention, dead-letter recovery, outbox, and schema compatibility. An event name is not a substitute for a full schema.
