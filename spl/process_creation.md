~~~
source:"WinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
Image="*(process).exe"
~~~
Insert given process into Image eg. "Image='*notepad.exe'", "Image='powershell.exe'"
