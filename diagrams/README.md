# Diagrams — Monitoring + Alerts + KQL Lab

This folder contains architecture diagrams that explain how monitoring data flows from `vm-mgmt-01` into Log Analytics, and how Azure Monitor alerts notify via an action group.

## Diagram 1 — End-to-End Monitoring Flow (VM → Logs → Alert → Email)

### Mermaid (rendered by GitHub)
```mermaid
flowchart LR
  VM[vm-mgmt-01\n(Existing VM)] -->|Azure Monitor Agent (AMA)\nvia VM Insights + DCR| LAW[Log Analytics Workspace\nlaw-monitoring-lab]
  LAW -->|KQL Queries\nHeartbeat / Logs| LOGS[Logs (KQL)]
  LAW -->|Log Alert Condition\nHeartbeat missing > 15m| ALERT[Alert rule\nalert-heartbeat-missing-vm-mgmt-01]
  ALERT -->|Action group| AG[ag-email-monitoring]
  AG -->|Email notification| EMAIL[Email inbox]

