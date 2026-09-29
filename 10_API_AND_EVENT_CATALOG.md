# API and event catalog

Status: Contract inventory; endpoints unapproved

## Candidate API groups
Identity/session; organizations and membership; spaces/projects; documents and versions; assets; templates/brand; comments/reviews; workflow runs; render jobs; delivery; audit/admin.

## Minimum contract fields
Operation ID; method/route or RPC; owner; auth scope; request/response schema; errors; pagination; rate limits; idempotency key; version policy; observability.

## Event envelope proposal
`event_id`, `event_type`, `schema_version`, `occurred_at`, `tenant_id`, `aggregate_id`, `correlation_id`, `causation_id`, `actor`, `idempotency_key`, `payload`, `before_ref`, `after_ref`.

## Reliability rules to decide
Outbox publishing, consumer deduplication, ordering scope, replay policy, dead-letter handling, schema compatibility, and retention. Publish event facts after committed state changes.
