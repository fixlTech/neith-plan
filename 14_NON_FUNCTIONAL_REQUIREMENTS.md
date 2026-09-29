# Non-functional requirements

Status: Targets pending workload and customer validation

| Quality | Metric to agree | Evidence method |
| --- | --- | --- |
| Availability | Monthly service and editor availability | Synthetic checks and SLO reports |
| Latency | p95 load/edit/save/preview times by project size | Real-user and load tests |
| Scale | Concurrent editors, assets, job throughput | Capacity tests |
| Durability | Acceptable data-loss window | Backup and fault tests |
| Recovery | Recovery time by failure class | Disaster drills |
| Security | Tenant isolation and incident response times | Threat tests and exercises |
| Accessibility | Target standard and supported workflows | Manual and automated audit |
| Compatibility | Supported formats, browsers, devices | Matrix tests |
| Observability | Trace coverage and alert response | Operational review |

Assign numeric thresholds, priority tier, measurement window, and owner before these become release gates.
