```
source="WinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 (Image="*whoami.exe" OR Image="*hostname.exe" OR Image="*ipconfig.exe"
OR Image="*arp.exe" OR Image="netstat.exe" OR Image="*nslookup.exe" OR Image="*powershell.exe" OR Image="*certutil.exe") NOT ParentImage="*splunkd.exe"
NOT Image="*splunk-powershell.exe"|table _time User Image ParentImage CommandLine |sort _time
```
