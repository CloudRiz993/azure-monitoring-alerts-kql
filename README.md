# Azure Monitoring + Alerts (Log Analytics + KQL) — Azure Portal Only (AZ-104)

## Goal
Enable monitoring for an existing VM (`vm-mgmt-01`), send platform + guest signals to Log Analytics, and trigger an alert when heartbeat stops (validated end-to-end).

## Scenario
Operations needs visibility and alerting for a critical VM:
- Collect logs/metrics into **Log Analytics Workspace**
- Query via **KQL**
- Alert when the VM stops reporting heartbeats
- Notify via **Action Group (Email)**

## Architecture
- VM: `vm-mgmt-01` (existing)
- Log Analytics Workspace: `law-monitoring-lab`
- VM Insights + Azure Monitor Agent (AMA)
- Data Collection Rule (DCR) targeting the VM
- Log alert rule: `alert-heartbeat-missing-vm-mgmt-01`
- Action group: `ag-email-monitoring` (email)

See: `diagrams/README.md`

## What I implemented (Portal)
- Created Log Analytics Workspace and enabled VM monitoring (AMA/VM Insights)
- Created/linked DCR to collect required data
- Built KQL query for Heartbeat detection
- Created Log Alert Rule (15 min missing heartbeat)
- Created Action Group (email) and validated alert firing

## Evidence
- Evidence index: `screenshots/README.md`

## Documentation
- Deployment: `docs/deployment.md`
- Validation: `docs/validation.md`
- Troubleshooting: `runbooks/troubleshooting.md`
- Teardown: `teardown/teardown.md`

## Outcome
Demonstrates AZ-104 skills in monitoring + alerting: AMA/VM Insights, DCR concepts, Log Analytics, KQL, alert rules, and operational troubleshooting.
