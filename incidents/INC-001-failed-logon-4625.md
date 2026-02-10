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
**False Positive** – Intentional test activity / benign user behavior

## Response Actions
- No containment required (lab activity)
- Documented outcome and evidence for audit trail

## Evidence
See screenshots in `/screenshots`:
- `-inc-001-triggered-alert.jpeg`
- `--inc-001-alert-results.jpeg`

## Future Improvements
- Tune alert to trigger only when multiple failed logons occur within a short window (reduce noise)
- Add context fields (account/IP/host) to the alert output for faster triage

