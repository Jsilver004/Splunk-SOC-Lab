# Process Creation

Monitor Windows process creation events using Sysmon to identify executed applications and suspicious process activity

---

## Overview

Process creation events provide visibility into application execution, parent-child process relationships, and command-line activity. They serve as the foundation for many endpoint detections.

---

## MITRE ATT&CK

   | Technique | Description |
   |---|---|
   | T1059 | Command and Scripting Interpreter |
   | T1059.0001 | PowerShell |

---

## Data Sources

- Sysmon Event ID 1 (Process Creation)

---

## Attack Simulation

Executed cmmon Windows applications:

```cmd
powershell
cmd
notepad
taskmgr
```

## Detection Logic

Monitor Sysmon Event ID 1 for newly created processes

## SPL
```spl
source:"WinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
| table _time User Image ParentImage CommandLine
```
---
## Results

Splunk successfully detected each process creation event, including the executing user, parent process, and command line.

---

## Analyst Notes

Process creation telemetry is the foundation for detecting reconaissance, PowerShell activity, LOLBins, and other endpoint behaviors.

---
