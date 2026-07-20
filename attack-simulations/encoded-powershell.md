## Encoded Powershell

encoded-powershell.md

```markdown
#Encoded PowerShell Simulation


## Objective

Execute an encoded Powershell command to test detection of obfuscated script execution.

---

## Command

```powershell
$encoded=[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytes("whoami"))
powershell.exe -EncodedCommand
$encoded
