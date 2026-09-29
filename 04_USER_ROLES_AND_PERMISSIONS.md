# Roles and permissions

Status: Proposed policy model

## Scopes
Organization → space/workspace → project → document/asset. Explicitly define inheritance, sharing across scopes, guest access, and denial precedence.

## Candidate role bundles
Owner, administrator, billing administrator, creative lead, editor, contributor, reviewer, viewer, automation operator, security/audit reader. Bundles should map to capabilities rather than UI labels.

## Permission naming
`resource.action.scope` (example: `project.edit.assigned`). Define create, read, edit, delete, share, approve, render, publish, manage policy, and audit actions for each resource.

## Rules to resolve
Separation of requester and approver; who may publish; external reviewer limits; service identity privileges; temporary grants; role changes during an approval; asset licensing restrictions; cross-tenant sharing.

## Verification
Enforce authorization in services and test tenant boundaries and privilege escalation. UI hiding is a usability layer, not an access control.
