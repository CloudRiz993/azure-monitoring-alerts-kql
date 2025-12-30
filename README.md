# Azure Monitoring + Alerts (Log Analytics + KQL) — Azure Portal Only (AZ-104)

## Goal
Monitor an existing VM (`vm-mgmt-01`) using Azure Monitor + Log Analytics and trigger an email alert when heartbeat stops (availability signal).

Lab note: vm-mgmt-01 is the shared lab VM used across my portfolio for consistent monitoring and alert validation

## Scenario
Ops needs a simple, reliable alert for VM availability:
- Collect telemetry into a Log Analytics Workspace
- Validate ingestion using KQL (Heartbeat)
- Create a log alert that fires when Heartbeat is missing for >15 minutes
- Notify via an Action Group (Email)

## Architecture
- Monitored VM: `vm-mgmt-01` (existing from VNet/NSG lab)
- Log Analytics Workspace: `law-monitoring-lab`
- Data collection: VM Insights / Azure Monitor Agent (AMA) + Data Collection Rule (DCR)
- Alert rule: `alert-heartbeat-missing-vm-mgmt-01` (log search alert)
- Action group: `ag-email-monitoring` (email notification)

Diagram: `diagrams/README.md`

## What I implemented (Portal)
- Created Log Analytics workspace in `rg-monitoring-kql-lab`
- Enabled VM monitoring for `vm-mgmt-01` via VM Insights (AMA + DCR)
- Confirmed Heartbeat ingestion using KQL
- Built log alert rule for Heartbeat missing (>15 minutes)
- Created Action Group and validated notification delivery (email)

## Evidence
Screenshots are indexed here:
- `screenshots/README.md`

Key proof artifacts:
- Workspace created
- VM Insights enabled / connected to workspace
- Heartbeat visible in KQL
- Action group created
- Alert rule created
- (Optional) Alert fired + email received

## Documentation
- Deployment: `docs/deployment.md`
- Validation: `docs/validation.md`
- Troubleshooting: `runbooks/troubleshooting.md`
- Teardown: `teardown/teardown.md`

## Skills demonstrated (AZ-104 aligned)
Azure Monitor • Log Analytics • AMA/DCR concepts • KQL queries • Log alerts • Action Groups • Operational troubleshooting • Cost control (teardown)
