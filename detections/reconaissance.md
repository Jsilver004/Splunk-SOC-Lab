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

