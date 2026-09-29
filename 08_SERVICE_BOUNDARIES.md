# Service boundaries

Status: Logical domains; deployment units undecided

| Domain | Owns | Contract to define |
| --- | --- | --- |
| Identity/tenancy | Users, memberships, policy context | AuthN/AuthZ decisions |
| Project/creative core | Project metadata, composition versions, commands | Save, load, version events |
| Assets | Binary metadata, variants, lineage | Upload, resolve, search |
| Collaboration | Presence, comments, sessions | Subscribe, annotate |
| Brand/templates | Kits, rules, templates, bindings | Validate, instantiate |
| Workflow | Durable runs, tasks, approvals, retries | Start, resume, cancel |
| Rendering | Jobs, artifacts, presets | Preview/export jobs |
| Delivery | Destinations, publication results | Deliver/retry |
| Audit/operations | Immutable activity references, admin policies | Query, retention |

For each domain define source of truth, mutation authority, API/events, consistency model, SLO, failure recovery, and data retention. A logical domain need not become an independent microservice.
