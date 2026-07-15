# LOLBin Certutil Detection

## Objective

Detect execution of the built-in Windows Certutil utility.

--- 

## Overview

Certutil is a legitimate Windows certificate utility frequently abused by attackers to donwload files, encode/decode payloads, and evade application controls.

---

## MITRE ATT&CK

   | Technique | Description |
   |---|---|
   | T1218 | System Binary Proxy Execution |


---

## Data Source

Sysmon Event ID 1

---

## Attack Simulation

Executed a Certutil line from Command Prompt.

```cmd
certutil -urlcache -split -f https://example.com example.html
```

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/LOLbin/LOLbinAttack.png)

---

## Detection Logic

Monitor Sysmon Process Creation events for certutil.exe.


---


## SPL

```spl
source="WinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
Image="*certutil.exe"
| table_time User ParentImage
CommandLine
```

---

## Results

Certutil execution was successfully detected and logged.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/LOLbin/LOLbinAttackCaught.png)


Windows Defender also identified and blocked the suspicious activity.

---

## Analyst Notes

Legitimate administrators rarely execute Certutil interactively. Unexpected executions should be investigated.

