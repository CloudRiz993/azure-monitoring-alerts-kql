# Deployment (Azure Portal Only) — Monitoring + Alerts + KQL Lab

## Goal
Monitor an existing VM (`vm-mgmt-01`) using Azure Monitor + Log Analytics, validate data using KQL, and configure an alert with email notification.

## Resources used/created
- Resource Group: `rg-monitoring-kql-lab`
- Log Analytics Workspace: `law-monitoring-lab`
- Existing VM monitored: `vm-mgmt-01` (from networking lab)
- VM monitoring enablement: VM Insights (Azure Monitor Agent + DCR)
- Action group: `ag-email-monitoring`
- Alert rule: `alert-heartbeat-missing-vm-mgmt-01`

## Step 1 — Create Resource Group
Azure Portal → Resource groups → Create:
- Name: `rg-monitoring-kql-lab`

## Step 2 — Create Log Analytics Workspace
Log Analytics workspaces → Create:
- Resource group: `rg-monitoring-kql-lab`
- Workspace name: `law-monitoring-lab`

Evidence: `/screenshots/02-law-created.png`

## Step 3 — Enable monitoring on vm-mgmt-01 (VM Insights)
1. Virtual machines → open `vm-mgmt-01`
2. Monitoring → Insights → Enable/Configure
3. Select workspace: `law-monitoring-lab`
4. Complete setup (AMA + DCR handled by portal)

Evidence: `/screenshots/03-vm-selected.png`, `/screenshots/04-vm-insights-enabled.png`

## Step 4 — Confirm data is flowing
Workspace → Logs:
- Validate Heartbeat table returns entries for the VM

Evidence: `/screenshots/05-kql-heartbeat.png`

