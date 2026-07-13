# Reconaissance Detection

## Objective

Detect common Windows reconaissance commands used by attackers during the Discovery phase of an intrusion.

## Overview

Attackers frequently execute built-in Windows utilities to gather informaiton on a compromised system before attempting privilege escalation or lateral movement.

This detection identifies common reconnaissance commands using Sysmon Process Creation (Event ID 1).

---

## Mitre ATT&CK

   | Technique | Description |
   |---|---|
   | T1033 | System Owner/User Directory |
   | T1082 | System Information Discovery |
   | T1049 | System Network Configuration Discovery |
   | T1049 | System Network Connections Discovery |
   | T1018 | Remote System Discovery |

---

## Data Source
- Sysmon Event ID 1 (Process Creation)

---

## Simulated Commands

```cmd
whoami
hostname
ipconfig
arp -a
netstat -ano
nslookup google.com
```

---

## Detection Logic

The detection monitors Sysmon process creation events and identifies common discovery utilities executed on the endpoint.

## SPL

```spl

```

## Results

The dashboard successfully detected each reconaissance command executed during testing.

(SS)

Observed commands include:

- whoami
- hostname
- ipconfig
- arp
- netstat
- nslookup

---

## Analyst Notes

While these commands are commonly used by administrators, multiple discovery commands executed in rapid succession may indicate an attacker performing host reconnaissance. 

Analysts should correlate these events with Powershell activities, network connections, authentication events, and subsequent process execution.

---

## Related Dashboard

Security Overview

---

## Related Attack Simulation

attack-simulations/reconaissance.md
