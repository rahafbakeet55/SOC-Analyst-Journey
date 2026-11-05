# SOC L1 Alert Triage – TryHackMe

## Overview

This lab focused on the alert triage process within a Security Operations Center (SOC), simulating the responsibilities of a Level 1 SOC Analyst.

The objective was to investigate security alerts, assess their severity, collect relevant evidence, determine whether activity was malicious or legitimate, and document investigation findings.

**Platform:** TryHackMe  
**Learning Path:** SOC Level 1  
**Module:** SOC Team Internals  
**Room:** SOC L1 Alert Triage  
**Status:** Completed

---

## Skills Practiced

- Security Alert Triage
- Alert Prioritization
- Endpoint Investigation
- IOC Analysis
- Malware Identification
- Network Activity Analysis
- True Positive / False Positive Classification
- Security Incident Documentation

---

## Investigated Alerts

### 1. Double-Extension File Creation

**Severity:** High  
**Host:** LPT-HR-009  
**User:** S.Conway  
**Process:** chrome.exe

**Suspicious File:**
`cats2025.mp4.exe`

**File Path:**
`C:\Users\S.Conway\Downloads\cats2025.mp4.exe`

**Source URL:**
`https://freecatvideoshd.monster/cats2025.mp4.exe`

**Investigation Findings:**
- Identified a suspicious executable disguised using a double file extension.
- Verified the file's MD5 hash.
- Checked the file against VirusTotal.
- VirusTotal reported 51/71 security vendors detecting the file as malicious.
- The malware was identified as LummaStealer.

**Final Verdict:** True Positive

---

### 2. Potential Data Exfiltration

**Severity:** Critical

**Investigation Findings:**
- Investigated unusual network traffic involving Zoom domains.
- Reviewed the amount of transferred data:
  - 5.8 GB sent.
  - 5.2 GB received.
- Examined the source context: UK04 / MEETINGROOM.
- Identified the traffic as legitimate Zoom meeting activity rather than unauthorized data exfiltration.

**Final Verdict:** False Positive

---

### 3. Download from GitHub Repository

**Severity:** Low  
**Host:** LPT-IT-063  
**User:** G.Chandler

**Repository:**
`github.com/facebook/react`

**Network Context:**
VPN / DEVELOPERS

**Investigation Focus:**
- Reviewed the GitHub download alert.
- Examined the repository URL.
- Considered the user and network context during triage.

---

## Key Takeaways

This practical exercise reinforced the importance of:

1. Prioritizing alerts based on severity and potential impact.
2. Investigating evidence before assigning a final verdict.
3. Validating suspicious files using hashes and threat intelligence sources.
4. Distinguishing malicious activity from legitimate business operations.
5. Documenting findings to support escalation and incident response.

## Learning Outcome

Completed a hands-on SOC L1 alert triage exercise involving endpoint and network security alerts, evidence analysis, and alert classification.

The exercise demonstrated how a Level 1 SOC Analyst contributes to identifying genuine threats while reducing false positives and unnecessary escalations.

---

**Lab:** [SOC L1 Alert Triage – TryHackMe](https://tryhackme.com/room/socl1alerttriage)
