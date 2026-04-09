---
name: last9-debug
description: Debug production issues using Last9 observability data
---

# Debug Production Issues

When the user asks to debug a production issue, follow this workflow using Last9 MCP tools:

## Investigation Flow

1. **Start with the service summary** — call `get_service_summary` to see which services have elevated error rates or latency.

2. **Check for recent deployments** — call `get_change_events` to see if a deploy or config change correlates with the issue timing.

3. **Drill into the affected service** — use `get_service_performance_details` for p50/p90/p95 latency, error rate, and throughput.

4. **Check dependencies** — call `get_service_dependency_graph` to see if the issue is in the service itself or a downstream dependency.

5. **Look at exceptions** — call `get_exceptions` filtered to the service. If exceptions are found, use `get_service_traces` with the service name and time range to find individual traces with full stack traces.

6. **Search logs** — use `get_service_logs` for the affected service and time range to find error-level log entries.

7. **Check alerts** — call `get_alerts` to see if any alerts have fired for this service.

## Tips

- Always start broad (service summary) then narrow down
- Use `did_you_mean` if a service name lookup fails — it suggests correct entity names
- Correlate timestamps: compare exception `first_seen`/`last_seen` with change event times
- For database issues, use `get_databases` to check DB-level throughput and latency
