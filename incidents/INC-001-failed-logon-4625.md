# INC-001 – Failed Windows Logon Alert (Event ID 4625)

## Summary
A Splunk alert triggered for Windows Security Event ID 4625 (failed logon). Initial triage was performed to determine whether the activity was malicious or benign.

## Detection / Alert Source
- SIEM: Splunk Enterprise
- Data Source: Windows Security Event Logs (WinEventLog:Security)
- Alert: Failed Windows Logon Attempt Detected (Event ID 4625)
- Severity: Medium

## Triage Steps Performed
- Opened the triggered alert in Splunk and reviewed alert results
- Confirmed events were Event ID 4625 (failed logon)
- Reviewed time of activity, affected account, and originating host/source context
- Determined whether activity matched expected user behavior vs suspicious behavior

## Findings
- Failed logon events were generated intentionally during lab testing
- Activity originated from the local Windows host
- No indicators of unauthorized access were observed during this review

## Classification

The alert was reviewed and correlated with Windows Security Event IDs 4625 (failed logon) and 4624 (successful logon).

Analysis showed failed authentication attempts followed by a successful logon from the same host within a short time window.

The activity was attributed to intentional user behavior during lab testing of the detection and alerting workflow.

**Classification:** True Positive (Benign / Expected Activity)

## Impact Assessment

- No evidence of lateral movement was observed
- No persistence mechanisms were identified
- No unauthorized access beyond the test account
- Activity was limited to the local Windows host

Overall impact was assessed as low.

## Response & Closure

- No containment actions were required
- No remediation actions were necessary
- Alert retained for continued monitoring
- Incident documented and closed

## Evidence

See screenshots in `/screenshots`:
- `inc-001-triggered-alert.jpeg`
- `inc-001-alert-results.jpeg`
