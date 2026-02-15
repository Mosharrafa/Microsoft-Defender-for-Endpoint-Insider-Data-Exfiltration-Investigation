## Objective

Determine whether sensitive files were prepared locally.

## Query Used

```kql

DeviceFileEvents
| where DeviceName == "mde-test-03"
| where FolderPath contains "ProgramData\\backup"
| order by Timestamp desc
| project Timestamp, ActionType, FileName, FolderPath, InitiatingProcessFileName, InitiatingProcessCommandLine, InitiatingProcessAccountName

```
<img width="1140" height="552" alt="image" src="https://github.com/user-attachments/assets/97715430-5fa3-4be1-ac9a-54df6cd0d84c" />



## Findings

# Observed activity:

Files renamed inside hidden directory C:\ProgramData\backup

Process responsible: powershell.exe

Account: xerox_4123

# Files detected:

employee-data-temp2026

employee-data-20260215

## Analysis

Indicators of intentional preparation:

Hidden system directory used

File renaming behavior

Same script responsible

## Conclusion

Sensitive data was staged locally on the machine.
