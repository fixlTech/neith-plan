# System architecture

Status: Candidate boundaries, no stack selected

## Logical layers
Clients and editor shell → application/API layer → shared creative core and specialized engines → platform services (assets, collaboration, workflow, render) → data/storage/event infrastructure → enterprise controls.

## Proposed invariant
Human editing and automation should operate on compatible versioned composition data and use the same validation and render semantics. Service splitting and deployment topology are open decisions.

## Key contracts to design
Document schema/versioning; command and undo semantics; asset references; real-time synchronization; render snapshot; authorization context; event envelope; audit provenance.

## Failure boundaries
Specify offline behavior, concurrency conflicts, queue backlog, job replay, regional outage, and incompatible document migrations. Quantify scale only after workload evidence.

## Architecture approval
Record selected technology and tradeoffs in `15_ARCHITECTURE_DECISIONS.md`; map ownership in `08_SERVICE_BOUNDARIES.md`.
