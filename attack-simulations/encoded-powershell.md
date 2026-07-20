## Encoded Powershell

## Objective

Execute an encoded Powershell command to test detection of obfuscated script execution.

---

## Command

```powershell
$encoded=[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytes("whoami"))
powershell.exe -EncodedCommand
$encoded

```

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Threat%20Detection/EncodedPowershell.png)

## Expected Telemetry
- Sysmon Event ID 1 (Process Creation)

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Threat%Detection/EncodedPowershellDetect.png)

## Related Detection

detections/powershell_Oofuscateion.md
