# Splunk-SOC-Lab
A hands-on Security Operations Center (SOC) lab using Splunk Enterprise for log collection, threat detection, incident investigation, and dashboard development.

## Overview

This project documents the creation of a Security Operations Center (SOC) lab using Splunk Cloud and the Splunk Universal Forwarder. The objective is to collect Windows event logs, develop detection rules, investigate simulated attacks amd build dashboards that demonstrate common blue team workflows.

The repository follows the progression of a real SOC implementation, beginning with log collection and configuration before moving into detection engineering, incidenrt reponse and threat hunting.

## Objectives
- Build a functioning Splunk-based SOC lab
- Collect Windows Events Logs
- Configure the Splunk Universal Forward
- Develop SPL detection queries
- Simulate common cyber attacks
- investigate alerts
- Build SOC dashboards
- Document incident response procedures

## Lab Architecture

This lab consists of a Windows 11 endpoint configured with Sysmon and the Splunk Universal Forwarder. Endpoint telemetry is forwaded to Splunk Cloud ,where searches, detections, dashboards and threat hunting activities are performed.

## Environment/Technologies
- Splunk Cloud
- Windows 11
- Splunk Universal Forwarder
- Windows Event Logs
- SPL (Search Processing Language
- Sysmon
- Kali Linux
- Powershell

## Data Sources

The lab collects endpoint telemetry from a Windows system using:

- Sysmon (Event IDs 1 and 3 for Process Creation and Network Connection respectively)
- Windows Security Logs
- Windows System Logs
- Powershell

## Detection Rules

Detection content is organized within the 'detection/' directory and includes:

- Process Creation
- Reconaissance Activity
- Encoded PowerShell
- Certutil (LOLBin)
- Brute Force Authentication
- Network Connections
- USB Device Detection
- Privileged Logon

## Attack Simulation

Attack simulations were performed to generate realistic endpoint activity and validate detection logic.
Simulated behaviors include:

- Windows reconnaissance commands
- Encoded PowerShell executation
- Certutil execution
- Repeate failed logon attempts

## Dashboards

Splunk dashboards provide visualization for:
- Process Creation
- Failed Logons
- Network Connections
- PowerShell Activity
- Threat Timeline
- Reconaissance Commands

## Repository Structure

splunk-threat-hunting-lab/

|---attack-simulations/

|---configs/

|---dashboards/

|---detections/

|---docs/

|---incidents_reports/

|---screenshots/

|---spl/

|---threat-hunting/

|---README.md

## Future Improvements

Future enhancements may include:

- Additioal Sysmon detections
- Sigma rule integration
- MITRE ATT&CK coverage expansion
- Multi-endpoint log collection
- Detection tuning to reduce false positives
