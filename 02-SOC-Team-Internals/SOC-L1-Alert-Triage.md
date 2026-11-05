# SOC L1 Alert Triage – TryHackMe

## 1. Overview

This practical lab simulated the daily responsibilities of a Level 1 Security Operations Center (SOC) Analyst.

The objective was to investigate security alerts, prioritize potential threats, collect relevant evidence, analyze endpoint and network activity, and determine whether detected events represented genuine security incidents or legitimate business activity.

| Detail | Information |
|---|---|
| Platform | TryHackMe |
| Learning Path | SOC Level 1 |
| Module | SOC Team Internals |
| Room | SOC L1 Alert Triage |
| Status | Completed |
| Alerts Investigated | 3 |

## 2. Skills Practiced

- Security Alert Triage
- Alert Prioritization
- Endpoint Investigation
- Indicator of Compromise (IOC) Analysis
- File Hash Verification
- Network Traffic Analysis
- Threat Intelligence Validation
- True Positive / False Positive Classification
- Security Incident Documentation

## 3. Alert Investigations

### Alert 1: Double-Extension File Creation

**Severity:** High  
**Verdict:** True Positive

**Endpoint Details:**

- Host: `LPT-HR-009`
- User: `S.Conway`
- Process: `chrome.exe`

**Suspicious File:**

`cats2025.mp4.exe`

**File Path:**

`C:\Users\S.Conway\Downloads\cats2025.mp4.exe`

**Source Domain:**

`freecatvideoshd.monster`

**File MD5:**

`14d8486f3f63875ef93cfd240c5dc10b`

**Investigation Findings:**

- Identified a suspicious executable disguised as a video file through a double-extension technique.
- Examined the file location and its origin.
- Recorded the file's MD5 hash as an indicator for further investigation.
- Recognized the double-extension technique as a potential malware delivery method.
- Validated that threat intelligence results must match the investigated file's hash before being used as supporting evidence.

**Analyst Assessment:**

The suspicious executable and its delivery context indicated potentially malicious activity.

**Final Verdict:** True Positive

---

### Alert 2: Potential Data Exfiltration

**Severity:** Critical  
**Verdict:** False Positive

**Network Details:**

- Source IP: `192.168.45.66`
- Destination: `*.zoom.us`
- Network: `UK04 / MEETINGROOM`
- Data Sent: `5.8 GB`
- Data Received: `5.2 GB`

**Detection Context:**

The detection rule identified network activity involving 5 GB or more of outbound data transferred from a device to a destination within a day.

**Investigation Findings:**

- Investigated unusually high outbound network traffic.
- Reviewed the destination domain associated with Zoom.
- Examined the source network and its business context.
- Identified the network as a meeting-room environment.
- Determined that the traffic was consistent with legitimate Zoom meeting activity rather than unauthorized data exfiltration.

**Analyst Assessment:**

Although the traffic volume triggered a Critical alert, the investigation context supported legitimate business activity.

**Final Verdict:** False Positive

---

### Alert 3: Download from GitHub Repository

**Severity:** Low  
**Verdict:** False Positive

**Endpoint Details:**

- Host: `LPT-IT-063`
- User: `G.Chandler`
- Repository: `github.com/facebook/react`
- Network: `VPN / DEVELOPERS`

**Investigation Findings:**

- Reviewed the GitHub download alert.
- Examined the repository URL.
- Identified the repository as the official React project.
- Considered the user's development-related context.
- Evaluated the activity against the expected use of developer resources.

**Analyst Assessment:**

The repository and network context were consistent with legitimate development activity.

**Final Verdict:** False Positive

---

## 4. Investigation Summary

| Alert | Severity | Final Verdict |
|---|---|---|
| Double-Extension File Creation | High | True Positive |
| Potential Data Exfiltration | Critical | False Positive |
| Download from GitHub Repository | Low | False Positive |

**Total Alerts Investigated:** 3

**True Positives:** 1

**False Positives:** 2

## 5. Key Takeaways

This exercise reinforced several important SOC investigation principles:

1. Alert severity does not automatically determine whether an event is malicious.
2. Suspicious file extensions can indicate malware delivery attempts.
3. File hashes must be accurately validated before relying on threat intelligence results.
4. Network traffic volume must be evaluated alongside destination and business context.
5. Legitimate developer activity can trigger security alerts.
6. Accurate evidence collection and documentation are essential for effective alert triage.

## 6. Learning Outcome

Successfully completed three practical alert investigations, classified one True Positive and two False Positives, and practiced evidence-based security alert triage.

This exercise strengthened my understanding of how SOC Level 1 Analysts investigate suspicious activity, validate security events, distinguish genuine threats from legitimate operations, and support appropriate incident escalation.

---

**Lab:** [SOC L1 Alert Triage – TryHackMe](https://tryhackme.com/room/socl1alerttriage)
