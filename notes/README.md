### Phase 1 – Splunk SIEM Setup
- Installed Splunk Enterprise on a Windows host
- Logged into Splunk Web UI successfully
- Verified license status (500 MB/day free trial)
- Confirmed local server configuration via Server Settings
- Captured and uploaded setup verification screenshots

---

### Phase 2 – Log Ingestion (Splunk Universal Forwarder)
- Downloaded Splunk Universal Forwarder for Windows (64-bit)
- Installed the Universal Forwarder on the Windows host
- Configured the forwarder to send data to the local Splunk indexer (localhost:9997)
- Enabled collection of Windows Security Event Logs
- Verified Windows Security logs were successfully ingesting into Splunk
- Confirmed data flow using SPL searches for `WinEventLog:Security`

---

### Phase 3 – Detection Engineering (Event ID 4625)
- Generated intentional failed login attempts on the Windows host to create test data
- Used Windows Security Event ID 4625 to identify failed logon activity
- Verified failed logon events were ingesting and searchable in Splunk
- Configured a Splunk alert to detect failed logon activity
- Generated intentional failed login attempts again on the Windows host 
- Set alert trigger conditions, severity, and scheduling
- Confirmed the alert triggered and reviewed the resulting events
