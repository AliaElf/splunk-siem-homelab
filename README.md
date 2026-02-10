# Splunk SIEM Home Lab – Windows Failed Logon Detection

This project demonstrates an end-to-end SIEM workflow using Splunk, from log ingestion through detection, alerting, triage, and incident response.

The goal of this lab was to simulate how a junior SOC analyst would investigate and document a security alert.

---

## Environment
- SIEM: Splunk Enterprise
- Log Source: Windows Security Event Logs
- Forwarder: Splunk Universal Forwarder
- OS: Windows

---

## Project Walkthrough

### Phase 1 – SIEM Setup
Splunk Enterprise was installed and configured on a Windows host. License status and server settings were verified.

📄 Notes:  
- [Phase 1 Setup Notes](notes/README.md)

📸 Evidence:
- [SIEM Setup Screenshots](screenshots)

---

### Phase 2 – Log Ingestion
Windows Security Event Logs were forwarded to Splunk using the Splunk Universal Forwarder. Log ingestion was validated using SPL searches.

📄 Notes:  
- [Log Ingestion Notes](notes/README.md)

📸 Evidence:
- [Log Ingestion Screenshots](screenshots)

---

### Phase 3 – Detection & Alerting
A detection was implemented for Windows failed logon activity using Event ID 4625. The detection was converted into a scheduled Splunk alert and validated using real test activity.

📄 Detection:  
- [Failed Logon Detection (Event ID 4625)](detections/failed-logon-4625.md)

📸 Evidence:
- [Alert Configuration & Results Screenshots](screenshots)


---

### Phase 4 – Alert Triage & Incident Response
The triggered alert was triaged by reviewing event context and correlating failed and successful logon events. The activity was classified and documented in an incident report.

📄 Incident Report:  
- [INC-001 – Failed Windows Logon Alert](incidents/INC-001-failed-logon-4625.md)

📸 Evidence:
- [Triggered Alert & Event Correlation Screenshots](screenshots)

---

## Key Skills Demonstrated
- SIEM deployment and configuration
- Log ingestion and validation
- Detection and alert configuration
- Alert triage and event correlation
- Incident documentation and closure
