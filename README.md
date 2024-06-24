<h1>Active Directory Home Lab</h1>


# Description
In this lab, I walk through creating an active directory Home Lab environment using Oracle Virtual Box. This is a lab environment that I can use for further experimentation and projects. For the scope of this project, I installed Active Directory, Remote Access Service and DHCP service on a Windows Server virtual machine and configured an internal network with another client virtual machine that joined the domain created on the server.
<br />


# Languages and Utilities Used

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>
- <b>Active Directory</b>
- <b>Remote Access</b>
- <b>DHCP</b>

# Environments Used

- <b>Windows 10 Pro</b>
- <b>Windows Server 2019</b>

# Project walk-through:


### Overview diagram to represent my Homelab's configuration:
This is the model I followed while setting up my homelab. The homelab consists of a Windows 2019 server VM and a Windows 10 Pro VM which have been installed with VirtualBox
<img src="https://i.imgur.com/1PKmF7M.png" height="80%" width="80%" alt="Overview Diagram"/>



### Windows server internal IP configuration:
The Windows server VM is setup with an External and Internal network adapter in the Oracle VirtualBox Settings and the IP address for the internal network should be setup according to the diagram

<img src="https://imgur.com/oI1eimo.png" height="80%" width="80%" alt="IP configuration"/>


### Add Active Directory Domain Services:
Within the Windows Server Manager select the second option "Add roles and features" and procede through the menus selecting Active Directory Domain Services as shown above

<img src="https://i.imgur.com/er0jCXH.png" height="80%" width="80%" alt="Active Directory Domain Services"/>


### Setup Domain:
After installing there will be ⚠ symbol on the top right which will prompt you to create the domain or promote the server to domain controller. Choose a name and procede through the menus, choose a password, install and restart the computer

<img src="https://imgur.com/p4W0DSj.png" height="80%" width="80%" alt="Setup Domain"/>


### Admin Group and User Creation:
Naviate to Start>Active Directory Users and Computers>mydomain.com and create a new organizational unit "_ADMINS" for the admin account

<img src="https://i.imgur.com/PoERPhv.png" height="80%" width="80%" alt="Admin Group"/>
<img src="https://i.imgur.com/l7orIlp.png" height="80%" width="80%" alt="Admin User"/>

### Install Remote Access service:
Within the Windows Server Managar add another role. This time we are installing RAS. Select Remote Access on the screen above and check the box next to routing when it appears on one of the following pages. When it is done, click the "Tools" dropdown menu, select routing and remote access. From here select NAT on the first page. Click next. Lastly, use public interface to connect to internet and select your external network

<img src="https://i.imgur.com/IBlUdPy.png" height="80%" width="80%" alt="RAS"/>



### Install DHCP Service:
In the same way that we install Active Directory Domain Services and Remote Access Service, we will now install the DHCP server service. After installing, navigate to the Tools dropdown once and again and open the DHCP service. Under domain dropdown, right click on IPv4 and create a new scope. The following menus will be filled out according to our model.

<img src="https://i.imgur.com/SbTCQfz.png" height="80%" width="80%" alt="DHCP"/>
<img src="https://i.imgur.com/DUS4TGW.png" height="80%" width="80%" alt="DHCP1"/>
<img src="https://i.imgur.com/H0Nyx3Q.png" height="80%" width="80%" alt="DHCP2"/>
<img src="https://i.imgur.com/iGSPjKR.png" height="80%" width="80%" alt="DHCP3"/>
<img src="https://i.imgur.com/GPNRcKM.png" height="80%" width="80%" alt="DHCP4"/>

### Open Powershell:
For My lab environment, I used a script to add myself and fake users to my domain. Run Windows Powershell ISE as administrator and open the CREATE_USERS.ps1 file.
Make sure to change directory to the location of the downloaded script and "Set-ExecutionPolicy Unrestricted"

The script used is available [here](https://github.com/Masellers/ActiveDirectoryLab/blob/main/AD_PS-master.zip)

<img src="https://i.imgur.com/k1vQXcu.png" height="80%" width="80%" alt="Powershell script"/>




### Use Powershell Script to populate Active Directory with Users:

<img src="https://i.imgur.com/j9CAgTJ.png" height="80%" width="80%" alt="PowerShell"/>

### Login to client VM using newly created user - configure and test network:
We can use commands with cmd such as "ipconfig", "ping" and "whoami" to see that we are connected and that the DHCP services on our server correctly assigned our IP

<img src="https://i.imgur.com/pzkhqDj.png" height="80%" width="80%" alt="ipconfig"/>

<img src="https://i.imgur.com/RBRGzoL.png" height="80%" width="80%" alt="Client1"/>

<img src="https://i.imgur.com/6B1Q0pj.png" height="80%" width="80%" alt="Whoami"/>

# Conclusion
Finally, We have created a Server with Active Directory, Remote Access and DHCP services so that we could automate onboarding users via a Powershell script, used ipconfig to show we were connected and DHCP services were working correctly and successfully logged into our client machine using a user account we created with our script

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
