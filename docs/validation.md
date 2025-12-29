# Validation (Proof) — Monitoring + Alerts + KQL Lab

## Goal
Prove telemetry is collected for `vm-mgmt-01`, KQL returns results, and an alert rule is configured to notify via email.

## Evidence files
See `screenshots/README.md` for the full index.

---

## A) Confirm VM is connected to monitoring
1. Open `vm-mgmt-01`
2. Monitoring → Insights shows enabled/configured
3. Workspace selected: `law-monitoring-lab`

Evidence: `04-vm-insights-enabled.png`

---

## B) Prove Heartbeat data exists in Log Analytics (KQL)
Workspace → Logs, run:

```kql
Heartbeat
| summarize LastHeartbeat=max(TimeGenerated) by Computer
| order by LastHeartbeat desc

