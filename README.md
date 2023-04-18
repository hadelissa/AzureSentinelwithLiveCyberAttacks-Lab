<h1>Azure Sentinel Live Cyber Attacks Home Lab</h1>


<h2>Description</h2>
In this lab I configured Azure Sentinel SIEM and linked it to a running virtual machine that was set up as a honey pot. By doing so, I was able to monitor RDP Brute Force attacks from various locations worldwide. Additionally, I have used a customized PowerShell script that retrieves geolocation details of the attackers and displays them on the Azure Sentinel Map.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell: Extract RDP failed logon logs from Windows Event Viewer</b> 
- <b>ipgeolocation.io: IP Address to Geolocation API</b> 


<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Azure</b>
- <b>Remote Desktop Connection</b>

<h2>Creating a Virtual Machine on Azure walk-through:</h2>
***To start this Lab you need to create Azure subscription(It's free, you get $200 worth of free credits by signing up OR use your student account)***

<p align="center">
Create a VM: this VM is going to play the role of a Honeypot that will be exposed to the internet to see the process of attackers trying to gain access to the VM as we disable the firewall to make it vulnerable and discoverable on the internet. <br/>
<img src="https://i.imgur.com/tnZFnRF.png" height="80%" width="80%" alt=""/>
<br />
<br />
Click on the Create button: <br/>
<img src="https://i.imgur.com/tnZFnRF.png" height="80%" width="80%" alt=""/>
<br />
<br />
Create a New Resource Group: To have everything we're going to use for this lab in the same lifespan: <br/>
<img src="https://i.imgur.com/ynBscZY.png" height="80%" width="80%" alt=""/>
<br />
<br />
Configure your settings as follow: Create your Adminstrator account with something that you can remember! we'll be using it to login to the VM later. Then, click Next:Disks> Next>Networking  <br/>
<img src="https://i.imgur.com/CAqCmXi.png" height="80%" width="80%" alt=""/>
<br />
<br />
On the NIC network security group, click on Advanced. Next, on the Configure Network group click Create New: <br/>
<img src="https://i.imgur.com/h7NKkVC.png" height="80%" width="80%" alt=""/>
<br />
<br />
Remove the existing firewall by clicking on the three dots then click remove. Click on the + Add an inbound rule and configure it as follow then Click Add (by doing this step it's going to allow attackers to try to gain access to the VM): Once you configure the following settings click OK. <br/>
<img src="https://i.imgur.com/eRvMwtq.png" height="80%" width="80%" alt=""/>
<br />
<br />
 Click Review + Create: Once you review your configuration Click Create. <br/>
<img src="https://i.imgur.com/95DofSd.png" height="80%" width="80%" alt="description"/>
<br />
<br />
 
 <h2>Creating Log Analytics workspace walk-through:</h2>
 
 <p align="center">
Now, Let's Create a Log Analytics Workspace: By doing this step we'll be able to create custom log that contains geographic information to discover where the attackers are coming from. <br/>
<img src="https://i.imgur.com/w3GVvTj.png" height="80%" width="80%" alt="description"/>
<br />
<br />
Click on Create Log Analytics Workspaces: <br/>
<img src="https://i.imgur.com/FWCKVF7.png" height="80%" width="80%" alt="description"/>
<br />
<br />
Configure the setting as follow: Choose the Group source that we have created previously, then Name your workspace. Once you're done click on Review + Create: <br/>
<img src="https://i.imgur.com/rdDMgyn.png" height="80%" width="80%" alt="description"/>
<br />
<br />
Review your configuration then click Create: <br/>
<img src="https://i.imgur.com/6bLO9kL.png" height="80%" width="80%" alt="description"/>
<br />
<br />
 
 <h2>Microsoft Sentinel walk-through:</h2>
 
  <p align="center">
tittle: <br/>
<img src="image source" height="80%" width="80%" alt="description"/>
<br />
<br />
 tittle: <br/>
<img src="image source" height="80%" width="80%" alt="description"/>
<br />
<br />tittle: <br/>
<img src="image source" height="80%" width="80%" alt="description"/>
<br />
<br />tittle: <br/>
<img src="image source" height="80%" width="80%" alt="description"/>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
