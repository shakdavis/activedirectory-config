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
Step 1. Create a resource group labeled "Active-Directory-Lab" in Microsoft Azure. For this tutorial, you could deploy your resource group in the EAST US 2 region.
  
Step 2. Within the resource group, create and deploy 2 virtual machines - one virtual machine acting as the Domain Controller or "DC-1" and operating under Windows Server 2022 and the other acting as your Active User or "Client-1" and operating under Windows 10 (21H2). After verifying both vms are going to be deployed and stored in the same region (ex. EAST US 2), you then create and deploy your virtual machines.

Step 3. Be sure to set the Domain Controller's NIC Private IP address to "STATIC". Since Client-1 will be using DC-1 as the DNS Server, this prevents DC-1's private IP address from changing. This can be done by going to DC-1's network settings in Azure > selecting the Network Interface Configuration with a computer chip icon > Settings tab > under IP Configurations tab select "ipconfig" hyperlink > change Private IP address setting to "Static" > be sure to save progress.

Step 4. To ensure both vms are operating along the same newtowrk, set Client-1 DNS settings to DC-1 private ip address.This can be done by going to DC-1's network settings in Azure > selecting the Network Interface Configuration with a computer chip icon > select Settings tab > under DNS servers tab select "Custom" and paste DC-1 private IP address inside textbox > be sure to save progress.
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Stebs"/>
</p>

<p>
Step 5. You're now going to run the Windows Remote Desktop and access your Domain User (DC-1) account using DC-1's public IP address. Use your credentials created during the making of the DC-1 vm to login. Once inside, you will now access the Server Manager which you could find using your start menu. Go to "Add Roles and features" > for the Server Selection = DC-1 > under the Server Roles tab, check Active Directory Domain Services and its features for installation.

Step 6. Once Active Directory is installed, there should be a pop-up in the top right corner to promote DC-1 as the actual domain controller. Clicking this will then bring up the Active Directory Domain Services Configuration Wizard. In the Deployment Configuration window, select "Add a New Forest" and the root domain name will be *mydomain.com* > for the Directory Services Restore Mode, for both password textboxes use *Password1* for now > proceed with "next" as nothing else changes and *install* at the end to install the forest. Your end result should inform you that the server was successfully configured as a domain controlle. You'll also receive a prompt about the network automactically restarting to complete to Active Directory installation. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 7. After about a few minutes, try logging back into your DC-1 network.
Step 8. 
</p>
<br />
