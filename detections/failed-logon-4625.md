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

## Evidence
Screenshots of the detection query and results are available in the `/screenshots` directory.

