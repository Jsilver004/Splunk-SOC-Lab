# Command Analysis

## Objective

Analyze commandline activity to identify suspicious/malicious command execution commonly used in attack discovery.

---

## Overview

Command-line telemetry can reveal reconaissance, encoded PowerShell, LOLBins, and other attacker techniques. Splunk was used to identify frequently executed command lines.

---

## Investigation

- Review command-line arguments
- Identify frequently executed commands
- Detect encoded PowerShell executions
- Correlate commands with parent processes

---

## Experiment

Commonly ran Account Discovery commands are utilized in PowerShell,

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADPage.png)
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADCommandsEntered.png)
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADCommandsEntered.png)

Then, acting as a threat hunter, we consult Splunk for logs regarding these commonly used commands.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADSplunkCaptured.png)
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADSplunkCaptured2.png)

With this data, we can reason if an attack is being conducted and which user and machine may be responsible for it.

For an automated response, an alert can be set to detect these commands being entered in bulk in a short amount of time.

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/Acccount%20Discovery/ADAlert.png)

## Data Source

- Sysmon Event ID 1 (Process Creation)




---

## Analysis
