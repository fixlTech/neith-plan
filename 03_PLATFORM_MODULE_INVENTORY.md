# Neith — Platform Module Inventory

**Version:** 0.2 draft · **Status:** Candidate catalogue, not an implementation inventory

## Catalogue structure
`Module → Submodule → Feature → Capability → Permission code`. A module describes product responsibility; it does not automatically require a separately deployed service. Assign a stable ID, owner, data source, dependency, priority, and implementation evidence to each row during refinement.

| Module | Submodules | Representative features and capabilities | Candidate permission family |
| --- | --- | --- | --- |
| M01 Identity and tenancy | Account, session, organization, membership, entitlement | Sign in, invite, revoke, switch tenant, configure access | `identity.*`, `organization.*` |
| M02 Spaces/projects | Space, project, settings, archive | Create, list, move, archive, restore, manage collaborators | `space.*`, `project.*` |
| M03 Creative core | Document, composition, scene, command, version | Save/reopen, transforms, layers, undo, snapshots, schema migration | `document.*` |
| M04 Asset platform | Ingest, metadata, search, collection, variant, rights | Upload, validate, tag, find, reuse, replace, inspect lineage | `asset.*` |
| M05 Design | Canvas, layout, typography, vector | Place, align, style, group, constrain, export | `design.*` |
| M06 Image | Raster layers, adjustments, masks, effects | Crop, retouch, composite, compare, preserve source | `image.*` |
| M07 Video | Timeline, tracks, transitions, captions, color | Trim, arrange, sync, preview, render | `video.*` |
| M08 Motion | Keyframes, animation, effects, compositing | Animate properties, interpolate, compose | `motion.*` |
| M09 Audio | Tracks, mixing, processing | Cut, gain, fade, sync, monitor, export | `audio.*` |
| M10 Shorts/reels | Aspect variants, reframing, presets | Derive vertical variants, captions, platform outputs | `shorts.*` |
| M11 Templates/components | Authoring, variables, instances, library | Publish version, bind, reuse, update safely | `template.*` |
| M12 Brand | Kits, rules, validation | Manage tokens/assets, inspect violation, override by policy | `brand.*` |
| M13 Collaboration | Presence, sharing, comments | Invite, observe, annotate, resolve | `collaboration.*` |
| M14 Review | Request, annotation, decision, history | Approve/reject frozen version, compare revisions | `review.*` |
| M15 Automation | Trigger, workflow, task, connector | Start, pause, retry, cancel, resume, inspect | `workflow.*` |
| M16 Render/delivery | Preview, export, queue, artifact, destination | Submit, cancel, download, publish, retry | `render.*`, `delivery.*` |
| M17 Enterprise | Policy, audit, retention, administration | Govern, inspect, export evidence, manage settings | `policy.*`, `audit.*` |
| M18 Insights/billing | Usage, reliability, quotas, subscription | View operational metrics and entitlements | `insights.*`, `billing.*` |

## Cross-module dependencies
The creative core uses asset references and identity context; specialized editors issue document commands. Templates and brand validation operate on versioned documents. Review binds to a frozen version. Render consumes an immutable snapshot and output preset. Automation coordinates those same contracts with retries and audit. Delivery refers to produced artifacts, not mutable editor state.

## Capability record template
`Mxx-Sxx-Fxx`: name, user job, inputs/outputs, preconditions, happy path, failure/edge cases, permission code and scope, owner, dependencies, API/events, measurable acceptance, release status, implementation evidence.

## Boundary questions
Decide whether image is a distinct app or an editor mode; how motion spans design and video; whether shorts is a workflow or app; which analytics and billing belong in first release; and how assets are licensed across organizations. Record decisions in `15_ARCHITECTURE_DECISIONS.md`.
