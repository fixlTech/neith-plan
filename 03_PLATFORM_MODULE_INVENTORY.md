# Platform module inventory

Status: Proposed taxonomy

| Domain | Submodules / capabilities | Key dependencies |
| --- | --- | --- |
| Identity and tenancy | Accounts, organizations, spaces, membership, entitlements | Security |
| Project and document core | Projects, compositions, command history, versioning, autosave | Storage, collaboration |
| Asset platform | Upload, metadata, search, collections, licensing, variants | Storage, indexing |
| Design and image | Canvas, vector/raster editing, layout, typography, effects | Core, assets |
| Video and motion | Timeline, transitions, compositing, animation, captions | Core, media processing |
| Audio | Tracks, mixing, effects, synchronization | Core, media processing |
| Short-form production | Reframing, presets, platform outputs | Video, audio, templates |
| Templates and brand | Components, variables, brand kits, validation | Assets, rendering |
| Collaboration | Presence, comments, sharing, conflict handling | Identity, versions |
| Review and approvals | Review states, annotations, sign-off | Collaboration, audit |
| Automation | Triggers, binding, workflow engine, retries, connectors | All production services |
| Render and delivery | Preview, export jobs, packaging, publishing | Engines, storage |
| Enterprise operations | Policy, audit, retention, analytics, admin | All domains |

Each module needs feature IDs, permission codes, ownership, service mapping, dependencies, and release status. Do not use this catalogue as proof that a module exists.
