<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
<img src="https://i.imgur.com/lNJH5eY.jpeg" alt="Microsoft Azure Logo"/>
<img src="https://i.imgur.com/WKG99uH.jpeg" alt="PowerShell Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure) with PowerShell</h1>
This project demonstrates how to implement and configure Active Directory Domain Services (AD DS) within Microsoft Azure Virtual Machines using PowerShell, simulating a real-world enterprise environment for centralized user management, authentication, and domain administration in a cloud-hosted infrastructure.<br />

<h2>Project Summary</h2>
This project serves as a tutorial and practical lab demonstrating the deployment of Active Directory Domain Services (AD DS) in a cloud-hosted environment using Microsoft Azure and PowerShell.
It showcases the installation, configuration, and management of a Windows Server domain, user accounts, and client domain joins, core skills for IT and cybersecurity professionals.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Active Directory Domain Services (AD DS)
- Azure Portal
- <img align="center" alt="PowerShell Icon" width="20px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/powershell-colored.svg" /> PowerShell
- Remote Desktop Protocol (RDP)

<h2>Operating Systems Used </h2>

- Windows Server 2025 Datacenter: Azure Edition
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1. Azure Resource Setup
- Step 2. Installing Active Directory Domain Services
- Step 3. Promoting to Domain Controller
- Step 4. Creating Organizational Units (OUs) and Admin Account
- Step 5. Joining Client-1 to the Domain
- Step 6. PowerShell Bulk User Creation
- Step 7. Remote Desktop Access Test

<h2>Deployment and Configuration Steps</h2>

<p>
<h3>Step 1. Azure Resource Setup</h3>
<img width="3832" height="3832" alt="image" src="https://github.com/user-attachments/assets/bf094d2b-63bc-45e1-8491-5d44f809b3fa" />
</p>
<p>
In the Azure Portal, two virtual machines (VMs) are created, dc-1 (the domain controller) and client-1 (the workstation). These VMs run inside Azure Compute and form the cloud environment used to build and test Active Directory Domain Services (AD DS) throughout the lab.
</p>
<br />

<p>
<h3>Step 2. Installing Active Directory Domain Services (AD DS)</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within Server Manager, the “Add Roles and Features” wizard is used to select and install the Active Directory Domain Services (AD DS) role on dc-1. This prepares the server to become a domain controller capable of managing users, groups, and authentication across the network.
</p>
<br />

<p>
<h3>Step 3. Promoting to Domain Controller</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After Active Directory Domain Services (AD DS) is installed, the Post-Deployment Configuration Wizard is launched to promote dc-1 to a domain controller and create a new forest named mydomain.com. This sets up the base of the Active Directory environment and enables centralized authentication (login control).
</p>
<br />

<p>
<h3>Step 4. Creating Organizational Units (OUs) and Admin Account</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers (ADUC), two Organizational Units (OUs) named _EMPLOYEES and _ADMINS are created to keep accounts organized. An admin account, jane_admin, is also added to the Domain Admins group to manage the domain securely.
</p>
<br />

<p>
<h3>Step 5. Joining Client-1 to the Domain</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The client-1 virtual machine is joined to the mydomain.com domain through System Properties, confirming successful communication with the domain controller. This step confirms that the domain controller and DNS are working correctly between the two virtual machines (VMs), allowing the client to log in with domain accounts.
</p>
<br />

<p>
<h3>Step 6. <img align="center" alt="PowerShell Icon" width="20px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/powershell-colored.svg" /> PowerShell Bulk User Creation</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In PowerShell ISE, the Generate-Names-Create-Users.ps1 script automatically creates 10,000 new user accounts in Active Directory. The _EMPLOYEES Organizational Unit (OU) in Active Directory Users and Computers (ADUC) shows the new users. This shows how PowerShell can save time by automating repetitive account creation tasks in Active Directory.
</p>
<br />

<p>
<h3>Step 7. Remote Desktop Access Test</h3>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A Remote Desktop Protocol (RDP) login test is done using one of the new employee non-administrative domain user accounts. Successful login confirms that domain authentication, permissions, and group policies are set up correctly for normal users.
</p>
<br />

<h2>Thank you for checking out my project!</h2>

<p>If you found it helpful or interesting, subscribe to my YouTube channel and connect with me on LinkedIn:</p>

[<img align="left" alt="Jeramy | YouTube" width="22px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/youtube.svg" />][youtube]
[<img align="left" alt="Jeramy | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" />][linkedin]

[youtube]: https://youtube.com/@jeramycanals
[linkedin]: https://linkedin.com/in/jeramycanals
