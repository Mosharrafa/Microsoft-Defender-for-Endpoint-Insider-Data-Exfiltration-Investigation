# Step 1 — Suspicious Script Execution (PowerShell)

## Objective
Confirm whether the user executed a suspicious PowerShell script consistent with insider data theft behavior.

---

## Investigation Logic
The investigation began by analyzing process execution telemetry to identify abnormal command-line activity.

PowerShell execution initiated by a user is a strong indicator of manual or scripted activity rather than normal background system behavior.

---

## Query Used

```kql
DeviceProcessEvents
| where Timestamp > ago(2h)
| where FileName in~ ("powershell.exe","pwsh.exe","cmd.exe")
| where ProcessCommandLine has_any (
    "exfiltratedata.ps1",
    "ProgramData\\exfiltratedata.ps1",
    "Invoke-WebRequest",
    "ExecutionPolicy Bypass",
    "ProgramData\\backup"
)
| order by Timestamp desc
| project Timestamp, DeviceName, AccountName, FileName, ProcessCommandLine, InitiatingProcessFileName
```

<img width="1211" height="741" alt="image" src="https://github.com/user-attachments/assets/0dc68a57-df26-4892-838a-fdf05dcfbb59" />


## Findings

The query revealed:

Device: mde-test-03

User: xerox_4123

Process chain: cmd.exe → powershell.exe

Suspicious execution parameters present




