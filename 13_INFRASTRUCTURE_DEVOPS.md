# Neith — Infrastructure and DevOps

**Status:** Deployment design checklist; cloud and cost model undecided

## Environments and isolation
Local development with representative services and seeded media; integration tests with disposable data; staging with production-like queues and object storage; production with protected credentials and operational ownership. Never use production customer media in lower environments without explicit controlled policy.

## Runtime components
API and auth boundary; document/data stores; object storage and CDN; upload and media-processing workers; workflow queue/orchestrator; realtime collaboration channel; search index; render workers with workload-aware scheduling; delivery connectors; logging, metrics, traces, alerts, and secrets management. Define regional placement and network boundaries when customer needs are known.

## Delivery pipeline
Lint/typecheck and meaningful tests → build immutable artifacts → scan and sign → deploy with feature flags → migrate compatibly → synthetic smoke checks → progressive traffic → observe SLO → rollback or forward fix. Schema and event changes require compatibility windows. Protect production branches and secrets.

## Operations
Assign on-call, alert thresholds, escalation, runbooks, capacity and cost dashboards, backup retention, restoration drills, job queue recovery, and incident communication. Test render surges, storage outages, queue poison messages, and credential expiry. Connect numerical RTO/RPO and availability objectives to `14_NON_FUNCTIONAL_REQUIREMENTS.md`.

## Artifacts to approve
Architecture and data-flow diagrams, environment inventory, IaC plan, CI/CD policy, deployment/rollback procedure, cost envelope, recovery exercise, and SLO ownership.
