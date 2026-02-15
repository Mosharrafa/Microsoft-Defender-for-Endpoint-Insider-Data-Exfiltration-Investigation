## Objective

Determine whether the data left the device.

## Query Used

```kql
DeviceNetworkEvents
| where DeviceName == "mde-test-03"
| where Timestamp between (datetime(2026-02-14 09:44:00) .. datetime(2026-02-14 09:48:00))
| order by Timestamp desc
| project Timestamp, RemoteIP, RemoteUrl, RemotePort, InitiatingProcessFileName, InitiatingProcessCommandLine

```
<img width="1221" height="605" alt="image" src="https://github.com/user-attachments/assets/36d745e7-bf3d-416d-883f-b70f9fae60f0" />

## Findings

No outbound network activity associated with the staging behavior was detected.

## Analysis

No evidence of:

Upload attempts

External connections

Data transfer

## Conclusion

Data was prepared but never transmitted.

## Final Investigation Conclusion

The user intentionally executed a script and staged sensitive company data locally.
However, there is no evidence the data was exfiltrated outside the machine.
