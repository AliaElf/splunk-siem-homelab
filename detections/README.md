Detection write-ups (SPL queries, logic, MITRE mapping, and screenshots).

# Detection: Failed Windows Logon Attempts (Event ID 4625)

## Objective
Detect failed authentication attempts on a Windows host to identify potential brute-force or unauthorized access activity.

## Data Source
- Windows Security Event Logs
- Event ID: 4625
- Collected via Splunk Universal Forwarder

## Detection Logic
```spl
index=* sourcetype="WinEventLog:Security" EventCode=4625
| stats count by Account_Name, IpAddress, Failure_Reason
| sort - count
```

## Evidence
Screenshots of the detection query and results are available in the `/screenshots` directory.

## Alert Configuration
A scheduled alert was created in Splunk to detect Windows failed logon events (Event ID 4625).

- Alert Type: Scheduled
- Schedule: Every 5 minutes (cron)
- Time Range: Last 15 minutes
- Trigger Condition: Number of results > 0
- Trigger Mode: Once
- Severity: Medium
- Permissions: Shared in App

The alert was successfully saved and enabled.

## Validation
This detection was validated by generating intentional failed login attempts on the Windows host.  
Event ID 4625 logs were successfully ingested, detected, and triggered a scheduled alert in Splunk.
