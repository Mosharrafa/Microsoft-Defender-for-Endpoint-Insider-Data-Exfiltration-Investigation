# Incident Scenario

## Background
A corporate employee was recently placed under a Performance Improvement Plan (PIP).  
Shortly after, management raised concerns that the employee might attempt to steal proprietary company data before resigning.

The employee had local administrator privileges and unrestricted application usage on the assigned workstation.

Security operations initiated a proactive threat hunting investigation to determine whether any sensitive data collection or exfiltration activity was taking place.

---

## Investigation Objective
Determine whether the employee:

1. Accessed sensitive files
2. Prepared or staged company data
3. Attempted to transfer the data outside the corporate environment

---

## Hypothesis
A potentially disgruntled insider may attempt data theft by:

- Collecting important files
- Compressing or renaming them
- Moving them to a hidden directory
- Uploading them to an external location

---

## Detection Strategy
To validate this hypothesis, endpoint telemetry from Microsoft Defender for Endpoint was analyzed across:

- Process execution logs
- File system activity
- Network connections

The investigation focused on identifying behavior consistent with insider data exfiltration techniques.

---

## Expected Outcome
If malicious activity existed, the investigation would reconstruct the full attack timeline and determine whether the data was successfully exfiltrated or only prepared for theft.
