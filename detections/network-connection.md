# Network Connection Detections

## Objective

Monitor outbound network connections created by processes.

---

## Overview

Processs establishing unexpected outbound connections may indicate malware, command-and-control acivitiy, or data exfiltration

---

## MITRE ATT8CK

   | Technique | Description |
   |---|---|
   | T1071 | System Owner/User Directory |
   |T1105 | |

---

## Data Source

Sysmon Event ID 3

---

## Attack Simulation

Executed PowerShell and generated outbound HTTPs traffic.

---

## SPL

```spl source=*WinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=3
Image="*powershell.exe"
|table _time Image DestinationIp DestinationPort CommandLine
```
   
---
## Results

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Connection%Monitoring/PowershellTest2.png)

Splunk Identified:

- Process Name
- Destination Port/IP
- Connection Timestamp

## Analyst Notes

Correlate with Process Creation events to determine what initiated the connection.




