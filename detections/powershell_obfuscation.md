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

---

## Data Source

- Sysmon Event ID 1 (Process Creation)

---

## Attack Simulation 

A Based64 'whoami' command was generated and executed.

```powershell
$encoded=[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytest("whoami")) powershell.exe -EncodedCommand $encoded
```

---

## Detection Logic

Searches Sysmon process creation events for PowerShell executions containing the '-EncodedCommand' argument.

---

## SPL 

```spl
source="WinEventLog":Microsoft-Windows-Sysmon/Operational'
EventCode=1
Image="*powershell.exe"
CommandLine="*-EncodedCommand*"
| table_time User Parentimage CommandLine
```

---

## Results

The econded PowerShell execution was successfully detected.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/EncodedPowershell.png)

Windows Defender also identified the activity as suspicious during testing.

## Analyst Notes

Encoded PowerShell is commonly associated with malware, download cradles, ransomware, and post-exploitation frameworks. While administrators occasionally use encoded commands, analysts should investigate unexpected executions.
