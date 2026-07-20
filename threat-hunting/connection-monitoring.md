# Connection Monitoring

## Objective

Observe current connection status of network devices to detect potentially suspicious connections and activities.

## Overview

Attacker commonly connect to services not regularly used by end users (Like PowerShell as admin). By searching out for these connections, we can potentially root an attack before it has time to occur.

## Investigation

- Act on PowerShell
- Check Splunk for detection

## Analysis

Before the attack, we can see no current commandine activity.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Connection%20Monitoring/PowershellSearch.png)

We then simulate an attacker and utilize powershell.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Connection%20Monitoring/PowershellTest.png)

After checking again, we can see a commandline was accessed now.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Connection%20Monitoring/PowershellTest2.png)



