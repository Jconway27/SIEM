<h1>SIEM</h1>



<h2>Description</h2>
Microsoft Azure Sentinel used to connect to a virtual machine (VirtualBox) acting as a honeypot. Observed live attacks on VM from around the world (well, until VM continued to drop [approximately 25-30 minutes]).
<br />


<h2>Languages and Utilities Used</h2>

- <b>Microsoft Azure</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Sentinel</b>

<h2>Homelab walk-through:</h2>

<p align="center">
1. Virtual machine created: <br/>
<img src="https://imgur.com/O6AxyV6.png" height="80%" width="80%"/>
<br />
<br />
2. Custom log created to ingest logs from the virtual machine which will contain geographic location:  <br/>
<img src="https://imgur.com/6rtwfr5.png" height="80%" width="80%"/>
<br />
<br />
3. Virtual machine logged into with jamesadmin: <br/>
<img src="https://imgur.com/dpuT5Pp.png" height="80%" width="80%"/>
<br />
<br />
4. Forced a failed login attempt from home pc to virtual machine for log analytics observed from virtual machine’s event viewer:  <br/>
<img src="https://imgur.com/UnVlJ1I.png" height="80%" width="80%"/>
<br />
<br />
5.Ping request from home PC to virtual machine timed out due to firewall status:  <br/>
<img src="https://imgur.com/dZhVGgk.png" height="80%" width="80%"/>
<br />
<br />
6. Virutal machine firewalls turned off to allow all in:  <br/>
<img src="https://imgur.com/8daoBXr.png" height="80%" width="80%"/>
<br />
<br />
7. Ping to virtual machine from home PC recieved:  <br/>
<img src="https://imgur.com/xyogHS4.png" height="80%" width="80%"/>
<br />
<br />
8. PowerShell script copied from Josh Madakor (YouTube). API key taken from ipgeolaction.io:  <br/>
<img src="https://imgur.com/MMSsSo2.png" height="80%" width="80%"/>
<br />
<br />
9. PowerShell running. Look through the event viewer for failed log ons, removed and sent to API, takes data and records in failed_rdp notepad:  <br/>
<img src="https://imgur.com/vjiqSYD.png" height="80%" width="80%"/>
<br />
<br />
10. Failed_rdp log in notepad:  <br/>
<img src="https://imgur.com/PVHqDmZ.png" height="80%" width="80%"/>
<br />
<br />
11. Failed RDP custom log created and running:  <br/>
<img src="https://imgur.com/kHB6kzo.png" height="80%" width="80%"/>
<br />
<br />
12. Data from log extracted to form map in Sentinel:  <br/>
<img src="https://imgur.com/3O8fwxg.png" height="80%" width="80%"/>
<br />
<br />
13. Final map (time lapse approximately half hour):  <br/>
<img src="https://imgur.com/BGBSVfK.png" height="80%" width="80%"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
