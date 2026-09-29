# Neith — Product Vision and Principles

**Version:** 0.2 draft · **Status:** Proposed; validate with user research

## Problem
Creative production often spans separate editing tools, asset stores, review channels, and export processes. Moving between them can lose context, create duplicate files, and make it difficult to know which version was approved or published. Neith's candidate opportunity is to provide coherent creation and production workflows across media types and team sizes.

## Vision
A creator should be able to start simply, grow into deeper editing, and work with a team or automated pipeline on the same underlying project and assets. Specialized apps should expose task-appropriate controls while preserving project identity, version lineage, and policy checks.

## Target personas and jobs
| Persona | Main job | Pain to validate | Candidate outcome |
| --- | --- | --- | --- |
| Independent creator | Produce social and campaign media quickly | Repetitive conversion and export | Reusable project and presets |
| Designer/editor | Refine visual and audiovisual work | Tool switching and fidelity loss | Deep controls with reversibility |
| Creative lead | Coordinate feedback and brand quality | Version ambiguity | Review and approve exact versions |
| Agency manager | Operate multiple client workspaces | Access and asset separation | Scoped roles and reusable templates |
| Enterprise operator | Run governed production at volume | Manual handoffs and weak audit | Durable workflows and traceability |
| Automation operator | Generate variants from approved inputs | Partial failures and duplicate delivery | Idempotent runs with human gates |

These are hypotheses, not evidence that each persona needs every module.

## Candidate product principles
1. **Shared foundation:** media apps work over compatible project, asset, identity, and version contracts.
2. **Progressive control:** common tasks are discoverable; advanced controls remain available without separate products.
3. **Non-destructive intent:** edits should preserve source assets and support undo, version comparison, and reproducible output; document unavoidable destructive operations.
4. **Trustworthy output:** preview, render, and export use defined color, timing, font, and media behavior.
5. **Collaboration with provenance:** comments and approvals refer to stable versions, actors, and timestamps.
6. **Accessible by design:** keyboard, assistive technology, and understandable feedback are part of core workflows.
7. **Policy at boundaries:** permissions and brand rules apply to both human and automated actions.
8. **Observable production:** long-running jobs show state, cause of failure, retry path, and final artifact.

## Candidate use cases
Create a branded design from a template; edit an image and reuse it in video; mix audio with a video timeline; make short-form variants; collect review comments on a frozen version; render and deliver approved outputs; generate a campaign from external data with validation and audit.

## Scope and non-goals to decide
The first supported workflow, import/export formats, collaborative editing depth, mobile editing depth, AI-assisted creation, stock licensing, marketplace, publishing destinations, and offline support have **no approved commitment here**. Record an explicit yes/no and rationale in the PRD rather than assuming an entire category ships.

## Competitive direction
Evaluate ease of use, editing depth, media interoperability, team review, templates, automation, governance, and cost against the products users actually replace. Avoid a blanket claim of superiority; run task-based comparisons with representative users.

## Success measures to establish
Time to first useful export; completion rate for first project; project reopening fidelity; repeat use of assets/templates; review turnaround; render success and time; automation completion without manual repair; accessibility task success; retention by persona. Set baselines, cohorts, thresholds, and measurement owners during discovery.

## Discovery gates
Interview each priority persona; observe at least one complete workflow; assess current code and customer constraints; rank jobs by frequency, pain, differentiation, and feasibility; approve the first release's target user and outcome. Link findings before changing this vision's status to Accepted.
