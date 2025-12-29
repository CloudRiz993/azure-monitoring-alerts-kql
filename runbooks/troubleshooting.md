# Troubleshooting Runbook — Monitoring + Alerts + KQL (Portal Only)

## Lab context (expected configuration)
- VM monitored: `vm-mgmt-01`
- Log Analytics workspace: `law-monitoring-lab`
- Resource group (monitoring): `rg-monitoring-kql-lab`
- Monitoring enablement: VM Insights (Azure Monitor Agent + DCR)
- Action group: `ag-email-monitoring`
- Alert rule: `alert-heartbeat-missing-vm-mgmt-01`

---

## Issue 1: Heartbeat table is empty (no data in Logs)

### Likely causes
- Propagation delay after enabling Insights/AMA
- VM is stopped/deallocated
- VM connected to a different workspace than expected
- Agent/DCR not successfully applied

### Checks (Portal)
1. Confirm VM is running:
   - Virtual machines → `vm-mgmt-01` → Overview → Status = Running
2. Confirm Insights is enabled and workspace is correct:
   - `vm-mgmt-01` → Monitoring → Insights → verify it is enabled and associated to `law-monitoring-lab`
3. Confirm in workspace Logs:
   - Log Analytics workspaces → `law-monitoring-lab` → Logs

### KQL checks
Run these in Logs:
```kql
Heartbeat
| take 10

