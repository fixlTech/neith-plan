# Neith — Frontend Architecture

**Status:** Proposed structure; framework and packages undecided

## Application shell
Organization and space context, routes, navigation, notifications, permissions, editor launch, and responsive layout. Feature packages expose Design/Image/Video/Audio/Motion/Shorts tools over a shared project/document client. Shared UI includes design system, asset picker, inspector, timeline primitives, job status, review controls, and accessible dialogs.

## State boundaries
Persisted composition and version IDs live in document state; in-flight commands and pending save status live in edit state; selection, viewport, panel layout, and hover are ephemeral or user preferences; comments and presence are collaboration state; render status is server-derived. Avoid treating a client cache as authority for permissions or approved versions.

## Editor command lifecycle
User gesture → validate command against mode/selection → update local preview → submit with base version/idempotency → reconcile acknowledged state → persist/notify → undo entry. Define coalescing, rejection rollback, conflict resolution, offline queue, and recovery. Mode changes must not discard pending edits silently.

## Loading and performance
Lazy-load specialized tools and heavy media workers. Virtualize large lists/timelines, limit memory, provide progressive thumbnails/waveforms, and measure startup, command latency, preview responsiveness, and memory by representative project size. Set numeric budgets in `14_NON_FUNCTIONAL_REQUIREMENTS.md`.

## Quality contracts
Typed API clients from reviewed contracts; error boundaries and retry UI; keyboard/focus mapping; screen-reader alternatives to canvas controls; browser/device matrix; telemetry with redaction. Produce route map, package boundaries, panel registry schema, component contracts, and a first-flow prototype before selecting implementation detail.
