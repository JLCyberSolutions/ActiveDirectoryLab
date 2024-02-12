<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
The purpose of this project is to create a home lab version of an Active Directory server that would emulate what you might find in a corporate environment. Virtualbox was utilized to create two VMs which would host two separate environments. The first VM was configured to have two separate network adapters (internal and external), and a Windows Server 2019 iso file was applied to it, allowing this VM to serve as the Active Directory Server and Domain Controller.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Oracle VirtualBox</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Windows Server 2019</b>

<h2>Project walk-through:</h2>

<p align="center">
This is a basic diagram of the full, configured network. The first VM, the domain controller (denoted DC) houses Active Directory and our domain (mydomain.com) via the installation of a Windows Server 2019 iso. This VM is configured to have two network adapters; one external adapter that connects to the internet, and one internal adapter that clients from inside the private network will connect to. The external network automatically receives IP addressing from my home router, while the internal network has IP addressing manually assigned to it. NAT and routing are configured on the domain controller allowing clients from the internal network to reach the internet through the domain controller. DHCP is configured with the info listed below so that our client machine (denoted CLIENT1, and using Windows 10) can automatically receive an IP address. CLIENT1 is joined to mydomain.com allowing any respective members to login and use this machine with their respective credentials. <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Viewing the dashboard of AD server manager and all configured services on the domain controller:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
DHCP enabled but still needs configuring: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
