# Response Actions

This section outlines the recommended response actions if this incident occurred in a real corporate environment.

The activity indicated malicious intent but no confirmed data exfiltration.  
Therefore the response focuses on containment, investigation, and prevention.

---

## Immediate Containment

### 1. Isolate the Device
Disconnect the endpoint from the network to prevent potential data transfer.

**Action (MDE):**
Endpoint → Isolate Device

---

### 2. Disable the User Account
Prevent further access by the suspicious user.

**Action:**
Entra ID / Active Directory → Disable Account

---

### 3. Preserve Evidence
Avoid rebooting or modifying the system before collecting forensic data.

Collect:
- Process logs
- File artifacts
- PowerShell history

---

## Investigation Expansion

### Check Data Access
Review whether the user accessed sensitive shares or repositories.

### Review Removable Media
Check USB activity logs to confirm whether data was copied locally.

### Review Cloud Activity
Investigate OneDrive, SharePoint, and email uploads.

---

## Remediation

### Remove Local Admin Privileges
Users should not have unrestricted administrative access.

### Restrict PowerShell
Enable PowerShell constrained language mode or logging.

### Implement Data Loss Prevention (DLP)
Block unauthorized file transfers.

---

## Monitoring Improvements

Create alerts for:

- File staging in system directories
- Execution policy bypass
- Large archive creation
- Unusual outbound connections

---

## Goal of Response

The goal is not only to stop the current incident but also prevent recurrence by improving security controls.
