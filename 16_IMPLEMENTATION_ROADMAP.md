# Neith — Implementation Roadmap

**Status:** Proposed dependency sequence; dates, staffing, and existing completion unknown

| Stage | Objective | Dependencies | Exit evidence |
| --- | --- | --- | --- |
| R0 Discover/audit | Validate personas, first workflow, and existing code | Source access and stakeholders | Approved scope; evidence ledger |
| R1 Foundation | Identity/tenancy, project, asset, document/version contracts | ADR-001/006 and threat model | Save/reopen with authorization and recovery |
| R2 First production slice | Selected editing surface, preview, export | R1, render contract | End-to-end user task and golden output tests |
| R3 Team workflow | Sharing, comments, review, templates/brand | Stable versions and permissions | Version-specific approval and revision tests |
| R4 Automated production | Durable campaign, render variants, delivery | R2/R3 and idempotent contracts | Failure/retry/approval/audit exercise |
| R5 Enterprise hardening | Policy/SSO as scoped, operations, resilience | Workload and customer requirements | Security, accessibility, load, restore gates |

These are logical dependencies, not a statement that all modules are unbuilt or that enterprise capabilities should wait wholesale until R5. Reconcile actual implementation first; move a completed slice to verified status only with evidence.

## Stage planning
For each stage define release outcome, included PRD IDs, owner, capacity, dependencies, demo scenario, measurable NFRs, risk, and exit criteria. Prioritize vertical user flows over isolated service construction. Keep migration and compatibility tasks alongside feature work.

## Change control
A stage changes when accepted requirements or evidence changes. Update PRD, module inventory, ADRs, tickets, tests, and this roadmap in one review. Estimates and dates belong in a staffed release plan, not invented here.
