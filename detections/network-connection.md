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

```spl

```
   
---
## Results

Splunk Identified:

- Process




![VLAN Creatio](../screenshots/Splunk/Dashboards/Suspicious%20Entries/SusBoard1.png)

