# Neith — Data Architecture

**Status:** Conceptual model; physical schema and stores undecided

## Core entities and relationships
Organization has memberships and spaces; Space has projects and policies; Project has documents; Document has immutable versions and command lineage; Version references assets and presets. Asset has immutable original, derived variants, metadata, checksum, rights, and lifecycle. Template and BrandKit have published versions. ReviewRequest targets one document version and gathers comments/decisions. WorkflowRun has steps, idempotency key, approvals, jobs, and delivery attempts. AuditRecord references actors, correlation, outcomes, and before/after versions.

## Ownership and storage
Domain owners in `08_SERVICE_BOUNDARIES.md` control writes. Binary media belongs in object storage with stable IDs/checksums and controlled URLs; metadata and policy use transactional records; search indexes are derived; caches are disposable. Select specific databases only after access patterns, scale, and failure needs are established.

## Versioning and lifecycle
Never mutate a published version or original asset in place. Define draft/autosave versus committed version, retention and garbage collection of unused media, legal hold, export/delete requests, and restore. Document schema changes need forward/backward compatibility rules, migration tests, and a fallback for clients opening newer versions.

## Data protection
Classify personal data, customer media, secrets, and audit records. Define encryption, tenancy partitioning, geographic residency, signed media access, key rotation, backup schedule, recovery point/time, retention, and deletion propagation to replicas and derived artifacts.

## Design deliverables
ERD with cardinalities; write-owner map; schema/migration definitions; storage and indexing selection; data lifecycle diagram; representative queries; backup restore exercise; reconciliation for orphaned assets and stuck jobs. Link accepted choices in ADRs.
