# Teardown (Azure Portal Only) — Monitoring + Alerts + KQL Lab

## Goal
Remove monitoring resources created for this lab without impacting the existing VM (`vm-mgmt-01`) from the networking lab.

## Step 1 — Remove alert rule
Monitor → Alerts → Alert rules:
- Delete `alert-heartbeat-missing-vm-mgmt-01`

## Step 2 — Remove action group
Monitor → Alerts → Action groups:
- Delete `ag-email-monitoring`

## Step 3 — Remove Log Analytics workspace
Log Analytics workspaces:
- Delete `law-monitoring-lab`

## Step 4 — Delete resource group (recommended)
Resource groups:
- Delete `rg-monitoring-kql-lab`

## Notes
- The VM `vm-mgmt-01` is not deleted in this teardown (it belongs to the VNet/NSG lab).

