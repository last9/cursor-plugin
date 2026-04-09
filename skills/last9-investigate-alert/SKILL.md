---
name: last9-investigate-alert
description: Investigate a firing alert using Last9 observability data
---

# Investigate Alert

When the user mentions a firing alert or wants to investigate an alert:

1. **List active alerts** — call `get_alerts` to see all currently firing alerts with severity, rule name, and current values.

2. **Get alert config** — call `get_alert_config` with the rule ID to understand what threshold or condition triggered the alert.

3. **Check the affected service** — use `get_service_performance_details` for the service mentioned in the alert to see current performance metrics.

4. **Correlate with deployments** — call `get_change_events` to check if a recent deploy caused the alert.

5. **Check logs around the alert time** — use `get_service_logs` filtered to the time window when the alert fired.

6. **Suggest remediation** — based on findings, suggest specific actions: rollback a deploy, scale a service, fix a query, etc.
