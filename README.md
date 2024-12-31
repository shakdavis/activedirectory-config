# activedirectory-config

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory: Configuration and Deployment within the Cloud (Azure)</h1>
This tutorial is a step-by-step guide on the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022 (Domain Controller)
- Windows 10 (21H2) (Active User / Client)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Creating virtual machines within Microsoft Azure: One for the Domain Controller (labeled DC-1) and one for the active user (labeled Client-1) 
- Step 2: Utilizing Windows remote desktop to access both DC and active user account; Initiating powershell to manage configurations. 
- Step 3: Creating our new Active User
- Step 4: Resetting Active User password

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="![Uploading Screenshot 2024-12-31 173907.png…]()"/>
</p>
<p>
Step 1. Create a resource group labeled "Active-Directory-Lab" in Microsoft Azure. For this lab, you could deploy your resource group in the EAST US 2 region.
Step 2. Within the resource group, create and deploy 2 virtual machines - one virtual machine acting as the Domain Controller or "DC-1" and operating under Windows Server 2022 and the other acting as our Active User or "Client-1" and operating under Windows 10 (21H2). After verifying both vms are going to be deployed and stored in the same region (ex. EAST US 2), you then create and deploy your virtual machines.

*IMPORTANT* Be sure to set the Domain Controller's NIC Private IP address to "STATIC". Since Client-1 will be using DC-1 as the DNS Server, this prevents DC-1's private IP address from changing. This can be done by going to DC-1's network settings in Azure > selecting the Network Interface Configuration with a computer chip icon > select "ipconfig" hyperlink > change Private IP address setting to "Static" </p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Stebs"/>
</p>

<p>
Step 3. In this image, Windows Remote Desktop service is being utilized. In utilizing this service I used this to gain access to both vms in order to see how the backend user (being DC-1) was able to allow and/or deny the frontend user (Client-1) access to certain programs and services over the network. I then matched up 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
