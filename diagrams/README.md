# Diagrams — Monitoring + Alerts + KQL Lab

## Diagram — End-to-End Monitoring Flow

```mermaid
flowchart LR
  VM["vm-mgmt-01<br/>(Existing VM)"]
  LAW["Log Analytics Workspace<br/>law-monitoring-lab"]
  LOGS["Logs (KQL)"]
  ALERT["Alert rule<br/>alert-heartbeat-missing-vm-mgmt-01"]
  AG["Action group<br/>ag-email-monitoring"]
  EMAIL["Email inbox"]

  VM -->|"Azure Monitor Agent (AMA)<br/>via VM Insights + DCR"| LAW
  LAW -->|"KQL queries<br/>Heartbeat / Logs"| LOGS
  LAW -->|"Log alert condition<br/>Heartbeat missing for 15 minutes"| ALERT
  ALERT -->|"Action group"| AG
  AG -->|"Email notification"| EMAIL
