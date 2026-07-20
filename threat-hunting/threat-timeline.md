# Threat Timeline

## Objective

Create a timeline of events an attacker does in order with timestamps to indicate when each occurred.

## Overview

Creating a threat timeline is essential for gaining an understanding of an attackers thought process, attack plan, and where to begin containment, eradication and remediation.

## Experiment

Simulating an attacker, a series of commands will be ran:
```spl
whoami
hostname
ipconfig
arp -a
netstat -ano
nslookup google.com
```

On the command line.

![VLAN Creatio](../screenshots/Splunk/Threat%20Timeline/Commands.png)

We will then search for occurrances of these commands and sort them in time order.

![VLAN Creatio](../screenshots/Splunk/Threat%20Timeline/TTSPL.png)

![VLAN Creatio](../screenshots/Splunk/Threat%20Timeline/Threat%20Timeline.png)

Using this, a threat hunter can piece together a threat actor's plan of attack, and figure out how to mitigate or put an end to it.


