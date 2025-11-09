<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
<img src="https://i.imgur.com/lNJH5eY.jpeg" alt="Microsoft Azure Logo"/>
<img src="https://i.imgur.com/WKG99uH.jpeg" alt="PowerShell Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure) with PowerShell</h1>
This project shows how to set up and configure Active Directory Domain Services (AD DS) on Microsoft Azure Virtual Machines (VMs) using PowerShell. It simulates a real-world enterprise environment where users, authentication, and domains are managed centrally in a cloud-hosted infrastructure.<br />
<p align="center">
  <img width="704" height="356" alt="image" src="https://github.com/user-attachments/assets/4b04b835-cb5b-436d-b8f4-92941ea54775" />
</p>

<h2>Project Summary</h2>
This project is a hands-on tutorial and practical lab that shows how to deploy Active Directory Domain Services (AD DS) in a cloud-hosted environment using Microsoft Azure and PowerShell.
It covers how to install, configure, and manage a Windows Server domain, create user accounts, and join client machines to the domain, core skills for IT and cybersecurity professionals.<br />
<p align="center">
<img src="https://i.imgur.com/Ew18HCW.png" alt="Project Summary"/>
</p>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Active Directory Domain Services (AD DS)
- Azure Portal
- <img align="center" alt="PowerShell Icon" width="20px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/powershell-colored.svg" /> PowerShell
- Remote Desktop Protocol (RDP)

<h2>Operating Systems Used </h2>

- Windows Server 2025 Datacenter: Azure Edition (24H2)
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

<h3>Step 1. Azure Resource Setup</h3>
<p>
<img width="3832" height="3832" alt="image" src="https://github.com/user-attachments/assets/bf094d2b-63bc-45e1-8491-5d44f809b3fa" />
</p>
<p>
In the Azure Portal, two virtual machines (VMs) are created, dc-1 (the domain controller) and client-1 (the workstation). These VMs run inside Azure Compute and form the cloud environment used to build and test Active Directory Domain Services (AD DS) throughout the lab.
</p>
<br />

<h3>Step 2. Installing Active Directory Domain Services (AD DS)</h3>
<p>
<img width="1920" height="1029" alt="image" src="https://github.com/user-attachments/assets/086ad8dc-17d4-4e66-9197-1393e53e3028" />
</p>
<p>
Within Server Manager, the “Add Roles and Features” wizard is used to select and install the Active Directory Domain Services (AD DS) role on dc-1. This prepares the server to become a domain controller capable of managing users, groups, and authentication across the network.
</p>
<br />

<h3>Step 3. Promoting to Domain Controller</h3>
<p>
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/5777a47a-a148-4dfa-8933-719b756e424b" />
</p>
<p>
After Active Directory Domain Services (AD DS) is installed, the Post-Deployment Configuration Wizard is launched to promote dc-1 to a domain controller and create a new forest named mydomain.com. This sets up the base of the Active Directory environment and enables centralized authentication (login control).
</p>
<br />

<h3>Step 4. Creating Organizational Units (OUs) and Admin Account</h3>
<p>
<img width="1910" height="329" alt="image" src="https://github.com/user-attachments/assets/787cbbf9-4596-4f27-95d2-4e64f2caa1d4" />
</p>
<p>
In Active Directory Users and Computers (ADUC), two Organizational Units (OUs) named _EMPLOYEES and _ADMINS are created to keep accounts organized. An admin account, jane_admin, is also added to the Domain Admins group to manage the domain securely.
</p>
<br />

<h3>Step 5. Joining Client-1 to the Domain</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The client-1 virtual machine is joined to the mydomain.com domain through System Properties, confirming successful communication with the domain controller. This step confirms that the domain controller and DNS are working correctly between the two virtual machines (VMs), allowing the client to log in with domain accounts.
</p>
<br />

<h3>Step 6. <img align="center" alt="PowerShell Icon" width="20px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/powershell-colored.svg" /> PowerShell Bulk User Creation</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In PowerShell ISE, the Generate-Names-Create-Users.ps1 script automatically creates 10,000 new user accounts in Active Directory. The _EMPLOYEES Organizational Unit (OU) in Active Directory Users and Computers (ADUC) shows the new users. This shows how PowerShell can save time by automating repetitive account creation tasks in Active Directory.
</p>
<br />

<h3>Step 7. Remote Desktop Access Test</h3>
<p>
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
<br clear="left"/>

[youtube]: https://youtube.com/@jeramycanals
[linkedin]: https://linkedin.com/in/jeramycanals
