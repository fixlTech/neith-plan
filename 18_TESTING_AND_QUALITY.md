# Testing and quality

Status: Proposed verification strategy

## Coverage
Domain unit tests; API/event contract tests; persistence/migration tests; end-to-end editing and review flows; import/export fidelity; media rendering comparisons; concurrent editing; accessibility; security/tenant isolation; load/soak; backup/recovery.

## Release evidence
Trace each approved requirement to at least one meaningful acceptance check. Keep reproducible fixtures for media, document versions, and workflow retries. Track defects and performance regressions with severity and ownership.

## Critical scenarios
Autosave interrupted mid-edit; conflicting edits; corrupt asset; permission revoked during operation; duplicate webhook; render worker crash; workflow approval timeout; failed delivery; migration rollback.
