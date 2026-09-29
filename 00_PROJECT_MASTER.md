# Neith — Project Master

**Version:** 0.2 draft · **Updated:** 2026-09-29 · **Document owner:** Product and architecture leads (to assign)

## 1. Purpose and authority
This is the entry point for planning Neith, a unified creative editing and mixing platform. It indexes the documents needed to define, build, test, and operate the product. The repository is a *planning baseline*, not evidence of a working implementation or approval of every proposal.

**Status vocabulary:** `Existing` requires code, deployment, or test evidence; `Accepted` requires a recorded decision and owner; `Proposed` is a design candidate; `Future` is outside an approved release; `Open` requires a decision; `Superseded` must link to its replacement. Each document should identify which status applies to its claims.

**Conflict order:** a dated accepted decision takes precedence over an older proposal; an approved requirement takes precedence over an unapproved example; implementation evidence describes reality but does not itself approve a product choice. If sources disagree, log the conflict in `91_OPEN_QUESTIONS.md` and avoid silently combining them.

## 2. Product definition
Neith intends to support design, image, video, motion, audio, and short-form production through specialized experiences over shared projects, assets, review, rendering, and enterprise controls. Audiences include individual creators, teams, agencies, and enterprise content operations. The precise launch scope, commercial model, supported formats, and performance commitments remain open.

## 3. Outcomes to validate
1. A creator can take an idea or source asset to a usable output with understandable controls.
2. A team can reuse brand assets, review a specific version, and trace approval and delivery.
3. An operator can run repeatable production with a resumable workflow and clear audit evidence.
4. Work can move between relevant tools without destructive conversion or unexplained data loss.

These are candidate outcomes. Set baselines and measurable success metrics through discovery before treating them as release commitments.

## 4. Document map
| Order | File | Decision or artifact it must produce |
| --- | --- | --- |
| 01 | `01_PRODUCT_VISION.md` | Users, jobs, principles, goals, exclusions, success measures |
| 02 | `02_PRODUCT_REQUIREMENTS_PRD.md` | Testable behavior, business rules, edge cases, acceptance criteria |
| 03 | `03_PLATFORM_MODULE_INVENTORY.md` | Module → submodule → feature → capability → permission catalogue |
| 04 | `04_USER_ROLES_AND_PERMISSIONS.md` | Scoped grants, role bundles, prohibited combinations |
| 05–06 | UX IA and workflows | Navigation, modes, end-to-end journeys and exceptions |
| 07–10 | System, services, data, APIs/events | Boundaries, ownership, contracts, lifecycle |
| 11–14 | Frontend, security, infrastructure, NFRs | Implementation constraints and measurable qualities |
| 15–19 | Decisions, roadmap, backlog, testing, release | Approved choices and delivery controls |
| 90–99 | Status, questions, debt, change log | Living evidence and governance |

## 5. Core lifecycle
Discovery → approve product scope → approve experience and domain contracts → audit existing code → sequence vertical implementation slices → verify requirements → stage and release → measure outcomes. Changes in approved scope must update affected requirements, contracts, acceptance tests, and decision records together.

## 6. Immediate work queue
1. Identify the current Neith source repositories and run an evidence-based implementation audit (`90_CURRENT_STATUS.md`).
2. Interview or validate priority personas and select an initial end-to-end workflow (`01`, `06`).
3. Decide first-release scope and non-goals (`02`, `03`).
4. Resolve document/version model, access scopes, media pipeline, and collaboration semantics (`15`).
5. Set measured non-functional targets with workload assumptions (`14`).
6. Derive executable tickets from accepted requirements (`17`).

## 7. Maintenance rules
Every requirement gets a stable ID, owner, priority, and test reference. Every major technical choice gets an ADR. Every claim that something is built links to evidence. Update this index and `99_CHANGELOG.md` when the authoritative baseline changes. Working discussions remain supporting material; these files hold the current agreed state.
