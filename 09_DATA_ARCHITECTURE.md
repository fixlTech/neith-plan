# Data architecture

Status: Conceptual model

## Candidate entities
Organization, User, Membership, Space, Project, Document, DocumentVersion, Command, Asset, AssetVariant, Template, BrandKit, Comment, Approval, WorkflowRun, RenderJob, Deliverable, AuditRecord.

## Ownership and references
Each aggregate has one write owner. Reference other domains by stable IDs and immutable version IDs where reproducibility matters. Store large media in object storage; define checksums and lineage; maintain explicit retention and deletion policies.

## Open technical choices
Document representation and schema evolution; relational/event data split; indexing strategy; collaborative operation model; version snapshots; geographic residency; backup and restoration; data export; legal hold.

## Design outputs
Entity relationship model, schema definitions, migrations, lifecycle diagrams, data classification, and recovery tests. Avoid choosing a database solely from this entity list.
