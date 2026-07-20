# Certutil Simulation

## Objective

Execute the Windows Certutil utility to validate LOLBin detection

---

## Command
```cmd
certutil -urlcache -split -f https://example.com example html
```
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Threat%20Detection/LOLbin/LOLbinAttack.png)


## Expected Telemetry

- Sysmon Event ID 1 (Process Creation)

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Threat%20Detection/LOLbin/LOLbinAttackCaught.png)

---

## Related Deteciton

detection/lolbin_certutil.md
