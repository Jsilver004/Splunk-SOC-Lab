# USB Detection

## Objective

Detect insertion of removable USB storage devices.

---

## Overview

USB devices may introduce malware or facilitate unauthorized data exfilitration.

---

## MITRE ATT8CK

T1091

---

## Data Source

Windows System Logs

---

## Attack Simulation

Inserted a SanDisk USB flash drive into my device.

![VLAN Creatio](../screenshots/Splunk/Dashboards/USB/USBInsert.png)

Then check Splunk to see if this action was detected.

---

## SPL

```spl
index=*
USB
```

## Results

Detected device insertion and information.

![VLAN Creatio](../screenshots/Splunk/Dashboards/USB/USBBoard.png)




