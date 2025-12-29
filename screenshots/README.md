# Evidence (Screenshots) — Monitoring + Alerts + KQL Lab

These screenshots prove end-to-end monitoring for `vm-mgmt-01` using Log Analytics, KQL, and Azure Monitor alerts.

## Files

| File | What it proves |
|---|---|
| `02-law-created.png` | Log Analytics workspace `law-monitoring-lab` created in `rg-monitoring-kql-lab` |
| `03-vm-selected.png` | Existing VM `vm-mgmt-01` selected for monitoring |
| `04-vm-insights-enabled.png` | VM Insights enabled and connected to `law-monitoring-lab` (AMA/DCR configured) |
| `05-kql-heartbeat.png` | KQL query returns Heartbeat for `vm-mgmt-01` |
| `06-action-group.png` | Action group `ag-email-monitoring` created with email notification |
| `07-alert-rule-created.png` | Log alert rule created for “heartbeat missing” and action group attached |
| `08-alert-fired.png` (optional) | Alert fired after stopping the VM long enough to miss heartbeat |
| `09-email-alert-received.png` (optional) | Email notification received from the alert |

