# Neith — UX Information Architecture

**Status:** Proposed navigation and interaction model

## Hierarchy
Organization contains spaces; a space contains projects and governed assets. Hubs group jobs; Apps expose specialized editing surfaces. An App opens a project/document rather than creating a separate copy of the same work. Proposed navigation: organization switcher → space → hub → app or project → editor. Confirm labels through usability research.

## Candidate hubs and app destinations
| Hub | Primary jobs | Candidate surfaces |
| --- | --- | --- |
| Create | Start or edit work | Design, image, video, audio, motion, shorts |
| Content | Reuse production inputs | Projects, templates, components |
| Media | Find and govern files | Asset library, collections, rights |
| Brand | Maintain identity | Kits, rules, validation |
| Review | Decide and annotate | Inbox, version comparison, approvals |
| Automate | Run repeatable work | Triggers, workflows, run history |
| Insights | Understand output | Usage, production health |
| Manage | Govern account | Users, permissions, policy, billing |

## Modes and switching
Quick presents common controls; Studio exposes deeper editing; Focus reduces chrome without removing work; Review locks editing of the reviewed snapshot; Preview simulates output; Automation configures bindings and runs. Before a switch, commit or preserve in-progress edits, warn on incompatible state, and keep selection/layout preferences separately from document content. A locked or unauthorized mode remains visible with an explanation only if discovery value outweighs confusion.

## Editor shell
Left navigation for tools/layers/assets; subheader for project, version, mode, save state; right inspector for selected object; bottom panel for timeline, audio, job status, or history when relevant. Panels respond to App, Mode, selection, role, viewport, and workflow lock through one registry. Keyboard navigation, focus restoration, and discoverable collapse controls are required.

## Responsive and accessible flows
Desktop supports full editing; mobile must define whether each operation is edit, review, preview, or read-only. Avoid merely shrinking panels. Specify touch targets, gestures with keyboard alternatives, captions/transcripts, screen reader labels, contrast, zoom, and reduced-motion behavior.

## Validation
Produce route map, screen inventory, wireframes, empty/loading/error states, prototype tests for first export and team review, and a panel visibility matrix. Record measured task completion and confusion before accepting this IA.
