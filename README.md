<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 - You want to creat your vertual machines in Azure, so that is VM-1 which we will call client-1 running om Windows 10, then VM2 which we will call DC-1 running on Windows server 2022, also make sure that both VM's are on the same Vnet.
- Step 2 - Then we will set the NIC for DC-1's private address to static which means the IP address will not change for as long as we need it for.
- Step 3 - Ensure there is connection between both machines so that we can deploy active directory.
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/rAap82H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here you can see that we created both machines in Azure, they are both up and running.
</p>
<br />

<p>
<img src="https://i.imgur.com/qWz7eNd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
So after creating the vertual machines we went in to change DC-1's NIC private IP address to static, to ensure that for as long as we need it, it does't change, to do this, in the Azure portal you will click on to DC-1, network, Network Interface, ipconfig, then you will change the status from dynamic to static.
</p>
<br />

<p>
<img src="https://i.imgur.com/0x3475T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After ensuring that DC-1's private IP address was changed from dynamic to static, we signed into DC-1 and enabled ICMPV4 communication between DC-1 and Client-1 in DC-1's local firewall, how we managed to this was after siginging in we hit the windows key, then typed wf.msc (miscrosft common console document) or you can also type in windows defender firwall, click on inbound rules, scrool over to protocals and sort to ICMPV4, and enable communication.
</p>
<br />

<img src=https://i.imgur.com/tBz0HCy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
So we signed into Client-1 to check the connectivity between DC-1 and Client-1 to do this, once you've signed into Client-1 tap the windows key and type command prompt, then ping DC-1's private IP address. 
