# Splunk SIEM Security Monitoring Lab

## Project Overview
Built a cybersecurity home lab using Splunk Cloud to investigate Windows authentication failures, visualize security events, and configure a detection alert.

## Tools Used
- Splunk Cloud Platform
- Windows 11 Pro
- Windows Event Viewer
- PowerShell
- Splunk Search Processing Language (SPL)
- UTM Virtualization

## 1. Windows Failed-Login Investigation

Exported Windows Security Event ID 4625 logs using PowerShell and imported them into Splunk Cloud for analysis.

**Findings:**
- Analyzed 8 failed-login events.
- Identified 7 events associated with time synchronization errors (`0xC0000133`).
- Identified 1 authentication failure (`0xC000006D`) with a username-not-found substatus (`0xC0000064`).

## 2. Security Monitoring Dashboard

Created a Splunk dashboard containing:
- Failed Login Attempts Over Time — column chart
- Authentication Failure Reasons — pie chart

These visualizations show authentication activity and categorize failure types.

## 3. Failed-Login Detection Alert

Configured a scheduled Splunk alert to detect 5 or more failed-login events within 15 minutes.

- Schedule: Every 15 minutes
- Trigger condition: Number of results greater than 0
- Action: Add to Triggered Alerts

**Limitation:** Logs were imported manually from CSV files. The alert is configured but has not yet been validated with live Windows log forwarding.

## Skills Demonstrated
- SIEM log analysis
- Windows Security Event investigation
- SPL queries
- Security dashboards
- Detection alert configuration
- Authentication troubleshooting

## Future Improvements
- Configure automatic Windows event collection.
- Test alert triggering with controlled lab events.
- Investigate additional Windows security event IDs.
