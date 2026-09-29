# Frontend architecture

Status: Proposed design concerns; framework undecided

## Layers
App shell/navigation; permission-aware routes; shared editor foundation; domain tools; design system; API clients; document state; media preview/render integration.

## Editor state
Separate persisted document state, local in-progress edits, selection, layout preference, and remote collaboration state. Define autosave, undo/redo, optimistic updates, conflict recovery, and mode switching with unsaved work.

## Performance
Set budgets for initial navigation, editor startup, interaction latency, memory use, large media, and low-end devices. Profile representative projects before setting targets.

## Deliverables
Route map; component contracts; panel registry schema; error/empty/loading states; accessibility test matrix; browser/device support; observability hooks.
