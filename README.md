<h1>Active Directory Home Lab</h1>


<h2>Description</h2>
In this lab, I walk through creating an active directory Home Lab environment using Oracle Virtual Box.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>
- <b>Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10 Pro</b>
- <b>Windows Server 2019</b>

<h2>Project walk-through:</h2>

<p align="center">
Overview diagram to represent Homelab: <br/>
<img src="https://i.imgur.com/1PKmF7M.png" height="80%" width="80%" alt="Overview Diagram"/>
<br />
<b>This is the model I followed while setting up my homelab</b>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use Powershell Script to populate Active Directory with Users:  <br/>
<img src="https://i.imgur.com/j9CAgTJ.png" height="80%" width="80%" alt="PowerShell"/>
<br />
<b>Make sure to change directory to the location of the downloaded script and "Set-ExecutionPolicy Unrestricted"
<br />
<br />
Observe New User With Whoami Command:  <br/>
<img src="https://i.imgur.com/6B1Q0pj.png" height="80%" width="80%" alt="Whoami"/>
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
