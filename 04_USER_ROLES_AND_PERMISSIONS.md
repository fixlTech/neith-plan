# Neith — User Roles and Permissions

**Status:** Proposed policy design; validate with security and customer workflows

## Actors and scope
Human users, invited guests, service identities, and external integration identities act within `organization → space → project → resource` scopes. A grant records subject, capability, scope, issuer, expiry, and conditions. Denial and restricted asset rights must take precedence over inherited broad grants. Evaluate access at execution time and record the policy version used.

## Candidate role bundles
| Role | Typical scope | Core grants | Restrictions |
| --- | --- | --- | --- |
| Organization owner | Organization | Manage membership, policy, billing delegation | Require strong authentication; audited actions |
| Administrator | Organization/space | Configure projects and access | Sensitive billing/security powers separated |
| Creative lead | Space/project | Manage work, review routing, templates | Publication may require separate grant |
| Editor | Project | Edit documents and assets | Cannot alter approval rules |
| Contributor | Assigned project | Upload/comment/limited editing | No broad sharing |
| Reviewer | Version/project | Read and decide review | No silent edit of reviewed version |
| Viewer | Project | Read permitted materials | No mutation/export unless granted |
| Automation operator | Space/workflow | Configure/run allowed jobs | Cannot bypass approval |
| Audit reader | Organization | Read audit evidence | No mutation of audit records |
| Billing administrator | Organization | Subscription and invoice controls | No automatic creative content access |

## Permission catalogue pattern
`resource.action` with explicit scope and conditions: `project.create`, `project.read`, `document.edit`, `document.version.read`, `asset.upload`, `asset.export`, `template.publish`, `brand.override`, `review.request`, `review.approve`, `render.submit`, `delivery.publish`, `workflow.configure`, `workflow.run`, `audit.read`, `membership.manage`. The policy service should publish a stable capability catalogue and map UI affordances to the same codes.

## Segregation and edge cases
Requester and approver may need separation; publication may require approval plus a publisher grant. Service identities have narrowly scoped grants, rotation, and no interactive ownership. Guests expire and cannot see unrelated tenants. Revocation invalidates future operations, while an in-progress long job must recheck at sensitive transitions. Sharing and copying across organizations require explicit rights and asset licensing checks. Define emergency override with expiry, reason, and audit.

## Verification
Test scope inheritance, explicit denial, role combinations, cross-tenant ID guessing, stale sessions, guest expiry, approval self-dealing, and automated action identity. The UI can hide disallowed actions but the API must enforce them.
