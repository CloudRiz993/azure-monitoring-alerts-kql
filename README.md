# Monitoring + Alerts (Log Analytics + KQL) — Azure Portal Only (AZ-104)

## Goal
Monitor an existing VM (`vm-mgmt-01`) using Azure Monitor + Log Analytics and trigger an email alert when heartbeat stops (VM down / agent stopped).

## Scenario
Ops needs a basic availability signal:
- Collect VM telemetry via Azure Monitor Agent (AMA) using VM Insights + DCR
- Query heartbeat data in Log Analytics (KQL)
- Fire a Log Alert when heartbeat is missing for 15 minutes
- Notify via Action Group (email)

## Architecture
- VM: `vm-mgmt-01` (existing from vnet/nsg lab)
- Log Analytics Workspace: `law-monitoring-lab`
- Data Collection Rule (DCR): VM Insights / AMA → LAW
- Alert rule: `alert-heartbeat-missing-vm-mgmt-01` (Log alert)
- Action group: `ag-email-monitoring` (email)

Diagram: `diagrams/README.md`

## Evidence
See `screenshots/README.md` for the proof index.

## Documentation
- Deployment: `docs/deployment.md`
- Validation: `docs/validation.md`
- Troubleshooting: `runbooks/troubleshooting.md`
- Teardown: `teardown/teardown.md`

## Outcome
Demonstrates AZ-104 skills in monitoring/observability:
Azure Monitor • Log Analytics • DCR/AMA • KQL • Log Alerts • Action Groups
