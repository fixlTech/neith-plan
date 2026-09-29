# Neith — System Architecture

**Status:** Logical architecture proposal; technology and deployment choices open

## Layers and responsibilities
Clients provide shell and editing controls; an API/application layer authenticates and orchestrates requests; Creative Core owns document representation, commands, versions, and references; specialized engines interpret image, design, video, motion, and audio operations; platform services manage assets, templates/brand, collaboration, review, workflow, render, and delivery; enterprise services govern policy, audit, and operations. Infrastructure supplies storage, queueing, realtime transport, search, observability, and compute.

## Invariants to decide and preserve
A saved version identifies schema, content, asset versions, author, and time. An output identifies the exact document/template/brand/preset versions that produced it. Human and automation operations pass through compatible authorization and validation. Source media is not overwritten by an edit. Every asynchronous command can be correlated with its resulting state and errors.

## Main data flows
Editor command → authorization → document mutation/version → event → collaboration notification. Asset upload → validation/transcode/metadata → stable asset reference → composition. Review request → snapshot → comments/approval → render eligibility. Workflow trigger → idempotent run → binding and validation → approval gate → render queue → artifact → destination → audit.

## Consistency and failure design
Choose concurrency semantics for document edits (single-writer, operational transform, or CRDT where justified), define version conflict and offline recovery, and distinguish synchronous acceptance from eventual media processing. Use transactional outbox or equivalent for durable state/event agreement. Render from immutable snapshots; consumers deduplicate messages. Document retry, cancellation, timeout, dead-letter, and restoration paths.

## Review gates
Approve document schema/versioning, asset lineage, service boundaries, API/event contracts, security model, availability targets, and cost/workload assumptions in ADRs. A diagram alone is insufficient; prove one vertical creation-to-export and one approval/retry flow.
