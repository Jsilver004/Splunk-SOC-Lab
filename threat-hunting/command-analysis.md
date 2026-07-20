# Command Analysis

## Objective

Analyze commandline activity to identify suspicious/malicious command execution.

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

## Data Source

- Sysmon Event ID 1 (Process Creation)




---

## Analysis
