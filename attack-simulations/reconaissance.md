# Reconaissance Attack Simulation

## Goal

Generate endpoint telemetry representing attacker discovery activity.

---

## Commands Executed

```cmd
whoami
hostname
ipconfig
arp -a
netstat -ano
nslookup google.com
```

--- 

## Expected Events

Sysmon Event ID = 1


## Detection

detections.reconaissance.md
