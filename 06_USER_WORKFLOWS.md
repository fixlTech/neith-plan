# User workflows

Status: Draft scenarios

## WF-01: Create and publish
Sign in → choose organization/space → create project → import or select assets → edit composition → save/version → preview → export → deliver. Specify failures for interrupted uploads, unsupported formats, lost connection, version conflict, and failed export.

## WF-02: Team review
Share a specific version → invite reviewer → annotate → request changes or approve → revise → compare versions → record final approval. Define who can approve and what invalidates approval.

## WF-03: Automated campaign
Receive authorized trigger → validate payload and template version → bind variables/assets → check brand and permissions → pause for approval if required → render outputs → deliver → write audit record. Retry idempotently and resume after pauses/failures.

## Workflow specification checklist
Actor; trigger; preconditions; data objects; commands and events; state transitions; permissions; compensation/retry; timeout; observability; acceptance examples.
