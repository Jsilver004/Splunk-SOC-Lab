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

![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/ADPage.png)
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/ADCommandsEntered.png)
![VLAN Creatio](../screenshots/Splunk/Threat%20Hunting/ADCommandsEntered.png)







## Data Source

- Sysmon Event ID 1 (Process Creation)




---

## Analysis
