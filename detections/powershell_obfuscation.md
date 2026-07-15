# PowerShell Obfuscation Detection

## Objective

Detect PowerShell processes launched using the '-EncodedCommand' parameter a common technique used to hide malicious script from users and security tools.

---

Attackers frequently execute Base64-encoded Powershell commands to conceal their intentions and bypass simple command command-line monitoring.

This detection identifies PowerShell executions containing the '-EncodedCommand' argument using Sysmon Process Creation logs.

---

## MITRE ATT&CK

   | Technique | Description |
   |---|---|
   | T1059.001 | PowerShell |
   | T1027 | Obfuscated Files or Information |

## Data Source

- Sysmon Event ID 1 (Process Creation)

```powershell
$encoded=[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytest("whoami")) powershell.exe -EncodedCommand $encoded
```

