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



![VLAN Creatio](../screenshots/Splunk/Process%20Creation/PowerShellOpen.png)

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/TaskManageOpen.png)




## Detection Logic

Monitor Sysmon Event ID 1 for newly created processes

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/NotepadCreate.png)


## SPL
```spl
source:"WinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
| table _time User Image ParentImage CommandLine
```
---
## Results

Splunk successfully detected each process creation event, including the executing user, parent process, and command line.

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/NotepadCreate2.png)

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/PowerShellDetected.png)

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/PowerShellDetected2.png)

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/TaskManageDetect.png)

![VLAN Creatio](../screenshots/Splunk/Process%20Creation/TaskManageDetect2.png)

---

## Analyst Notes

Process creation telemetry is the foundation for detecting reconaissance, PowerShell activity, LOLBins, and other endpoint behaviors.

---
