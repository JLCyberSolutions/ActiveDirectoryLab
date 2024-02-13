<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
The purpose of this project is to create a home lab version of an Active Directory server that emulates what you might find in a corporate environment. Virtualbox was utilized to create two VMs which host two separate environments. The first VM was configured to serve as the domain controller by applying a Windows Server 2019 iso to it, installing Active Directory, and creating mydomain.com. Remote Access Services and NAT were configured on the domain controller to allow users on the internal portion of the network a means to reach the internet. DHCP was also configured on the domain controller with a scope of 172.16.0.100-200 to automatically lease users of mydomain.com an IP address within that range. A powershell script focused on automatic user creation was ran on the domain controller and over 1000 randomly named accounts were created and added to the user list of mydomain.com. Finally, a second VM was created, a Windows 10 iso was applied to it, and the machine was renamed CLIENT1. CLIENT1 was joined to mydomain.com allowing any of the various user accounts to login with their respective credentials, receive an IP address, and begin using the workstation as needed. The various user accounts were additionally split into several security groups such as Accounting, Human Resources, IT, Sales, and Termed, with each group having their own set of permissions and access within mydomain.com.
<br />


<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Windows Server 2019</b> 

<h2>AD Services Enabled (delete?) </h2>

- <b>Routing via RAS</b>
- <b>NAT</b>
- <b>DHCP</b>

<h2>Project walk-through:</h2>

<p align="center">
Pictured below is a basic diagram of the full, configured network. The first VM, the domain controller (denoted DC) houses Active Directory and our domain (mydomain.com) via the installation of a Windows Server 2019 iso. This VM is configured to have two network adapters; one external adapter that connects to the internet, and one internal adapter that clients from inside the private network will connect to. The external network automatically receives IP addressing from my home router, while the internal network has IP addressing manually assigned to it. NAT and routing are configured on the domain controller allowing clients from the internal network to reach the internet through the domain controller. DHCP is configured with the info listed below so that our client machine (denoted CLIENT1, and using Windows 10) can automatically receive an IP address. CLIENT1 is joined to mydomain.com allowing any respective members to login and use this machine with their respective credentials. <br/>
<img src="https://i.imgur.com/2BNq92C.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
Viewing the dashboard of AD server manager and all configured services on the domain controller:  <br/>
<img src="https://i.imgur.com/G095HKu.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
DHCP enabled but still needs configuring: <br/>
<img src="https://i.imgur.com/kt0HOxz.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
DHCP configured with scope 172.16.0.100-200:  <br/>
<img src="https://i.imgur.com/yv9jrfE.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
The powershell user creation script to create 1k+ accounts:  <br/>
<img src="https://i.imgur.com/wzeD7oU.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
Automatic account creation in action:  <br/>
<img src="https://i.imgur.com/PLMNy8x.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
1051 total users after running script:  <br/>
<img src="https://i.imgur.com/jEC9dtO.png" height="80%" width="80%" alt="AD Home Lab"/>
<br />
<br />

<p align="center">
CLIENT1 created, joined to mydomain.com and automatically receiving IP address, subnet mask, default gateway, etc:  <br/>
<img src="https://i.imgur.com/uwAzTd3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
CLIENT1 showing on the domain controller as a result of being joined to mydomain.com:  <br/>
<img src="https://i.imgur.com/W93VU7w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
CSwisher, the random user account I chose to login to CLIENT1 with and test DHCP:  <br/>
<img src="https://i.imgur.com/ULPBkFa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
CSwisher logging in on CLIENT1:  <br/>
<img src="https://i.imgur.com/lmi0yr5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
CSwisher logged in on CLIENT1, command line shows CSwisher as a member of mydomain.com:  <br/>
<img src="https://i.imgur.com/WvLOmk0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Back on the domain controller with DHCP showing an IP address leased to CLIENT1 following CSwisher's login:  <br/>
<img src="https://i.imgur.com/4Zq8cfK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Active Directory control panel featuring the addition of the various security groups:  <br/>
<img src="https://i.imgur.com/dkKYubG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
