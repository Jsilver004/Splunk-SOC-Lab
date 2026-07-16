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
