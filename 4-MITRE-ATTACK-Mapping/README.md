# MITRE ATT&CK Mapping

This section maps the observed behavior during the investigation to the MITRE ATT&CK framework in order to understand attacker intent.

The investigation identified behavior consistent with an insider attempting to collect and prepare sensitive data before leaving the organization.

---

## Observed Activity

| Investigation Phase | Observed Behavior |
|---|---|
Execution | PowerShell launched from command shell
Collection | Script accessed company files
Staging | Files moved and renamed in hidden directory
Exfiltration | No outbound transfer detected

---

## Technique Mapping

---

### T1059.001 - Command and Scripting Interpreter: PowerShell

**Evidence**
- `cmd.exe` launched `powershell.exe`
- Execution policy bypass indicators present
- Script execution confirmed from endpoint logs

**Why it Matters**
Attackers commonly use PowerShell because it is built into Windows and does not require external malware.

---

### T1074.001 - Local Data Staging

**Evidence**
- Files stored in `C:\ProgramData\backup`
- Renamed before transfer
- Hidden directory usage

**Why it Matters**
Before stealing data, attackers prepare files in a single location to simplify transfer.

---

### T1041 - Exfiltration Over C2 Channel (Not Observed)

**Evidence**
- No related outbound network traffic detected
- No upload activity recorded

**Why it Matters**
Although preparation occurred, the attack did not reach the data theft stage.

---

## Attack Flow Representation

Initial Access → Execution → Collection → Staging → Exfiltration

Observed:

Execution → Collection → Staging → ❌ Exfiltration

---

## Security Insight

Detecting attacker preparation is often enough to prevent a breach.

In this case, monitoring endpoint behavior allowed identification of malicious intent before any data left the environment.
