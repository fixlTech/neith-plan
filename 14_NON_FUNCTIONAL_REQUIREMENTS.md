# Neith — Non-Functional Requirements

**Status:** Metric catalogue; numerical targets pending measured workload and product scope

Every target must specify cohort/device, project size, percentile, measurement window, owner, and release gate. Avoid a single latency number for a tiny design and a long 4K video.

| Quality | Proposed measurement | Acceptance method |
| --- | --- | --- |
| Performance | p50/p95 navigation, editor ready, command acknowledgement, save, preview, export queue time | Real-user monitoring and representative load tests |
| Availability | Monthly successful API/editor access by tier; render queue availability separately | SLO report and synthetic transactions |
| Scale | Concurrent editors, per-document collaborators, asset volume, queued renders, throughput | Capacity/soak tests with declared media mix |
| Reliability | Lost edits, job completion, duplicate delivery, retry recovery rates | Fault injection and production metrics |
| Durability | Maximum data loss for versions/assets and backup retention | Restore and checksum tests |
| Recovery | RTO/RPO by outage class; queue replay time | Timed regional/service drills |
| Security | Tenant-isolation failures, critical remediation time, key rotation | Penetration, authorization, and response exercises |
| Accessibility | Chosen WCAG target and task coverage across editors | Manual assistive-technology and automated audits |
| Compatibility | Browser/device/format/version matrix and import/export fidelity | Golden media fixtures and matrix runs |
| Maintainability | Change failure rate, migration duration, contract compatibility | CI and release telemetry |
| Observability | Traced critical flow coverage and actionable alert precision | Incident review and trace sampling |

## Workload profiles to define
Simple image/design; multilayer composition; long video with audio; collaborative session; bulk template campaign; render surge. Measure CPU/GPU, memory, storage, network, and cost. Set numeric thresholds only with target hardware and user research.

## Release policy
For each accepted target document threshold, test dataset, owner, monitoring query, and exception process. A feature cannot claim enterprise readiness solely because a dashboard exists.
