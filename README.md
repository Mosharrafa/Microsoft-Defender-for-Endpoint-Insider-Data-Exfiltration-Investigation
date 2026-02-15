# Microsoft-Defender-for-Endpoint-Insider-Data-Exfiltration-Investigation
Threat hunting investigation using MDE to analyze a suspected insider attempting data theft. Correlated process, file, and network telemetry with KQL, mapped activity to MITRE ATT&amp;CK, and determined the user staged sensitive data but failed to exfiltrate it. Demonstrates real SOC investigation workflow and response planning.




## Overview
This project simulates a real-world insider threat scenario where an employee attempts to steal sensitive company data before leaving the organization.

Using Microsoft Defender for Endpoint (MDE) advanced hunting, I performed a full forensic investigation including process analysis, file activity correlation, and network traffic verification.

The objective was to determine whether corporate data was successfully exfiltrated or only prepared for theft.

---

## Key Outcome
The investigation confirmed that the activity collected and staged sensitive data locally but did not successfully transfer the data outside the machine.

**Final Verdict: Attempted Data Exfiltration (Prevented)**

---

## Skills Demonstrated
- Threat Hunting
- Incident Investigation
- Log Correlation
- MITRE ATT&CK Mapping
- KQL Querying
- Endpoint Telemetry Analysis
- Incident Response Planning

---

## Tools Used
- Microsoft Defender for Endpoint
- Advanced Hunting (KQL)
- Windows Event Telemetry

---

## Attack Techniques Identified
| Technique | Description |
|--------|------|
T1059.001 | PowerShell Execution
T1074.001 | Local Data Staging

---

## Investigation Flow
1. Identify suspicious execution activity
2. Correlate file system modifications
3. Verify potential data exfiltration
4. Map behavior to MITRE ATT&CK
5. Propose containment actions

---

## Repository Structure
Each folder represents a phase of a real SOC investigation from detection to response.

This project demonstrates how security teams detect insider threats before a data breach occurs.

---

## Why This Matters
Many security incidents are prevented not by blocking attacks, but by detecting attacker preparation early.

This investigation shows how endpoint telemetry can stop data theft before impact.

