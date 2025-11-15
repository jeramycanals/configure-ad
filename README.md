<p align="center">
  <img width="298" height="166" alt="image" src="https://github.com/user-attachments/assets/dc3b64e1-0e71-4777-b07c-8f99e3245d5c" />
  <img width="297" height="65" alt="image" src="https://github.com/user-attachments/assets/499c27ec-8b27-47f7-9f60-c28191276562" />
  <img width="224" height="73" alt="image" src="https://github.com/user-attachments/assets/8af18f15-6dc2-4f98-ac96-d8e6b35d69de" />
</p>

<h1>Active Directory Deployed in the Cloud (Azure) with PowerShell</h1>

This project is a hands-on tutorial and practical lab that demonstrates how to deploy and configure Active Directory Domain Services (AD DS) in a cloud-hosted enterprise environment using Microsoft Azure Virtual Machines and PowerShell. It covers how to install, configure, and manage a Windows Server domain; create Organizational Units (OUs) and set up admin and user accounts; join client machines to the domain; and use PowerShell automation and Remote Desktop (RDP) to bulk-create and access users. This lab simulates a real-world IT environment where authentication, identity, and domain resources are centrally managed, which are core skills for IT and cybersecurity professionals.
<br />

<p align="center">
  <img width="704" height="356" alt="image" src="https://github.com/user-attachments/assets/4b04b835-cb5b-436d-b8f4-92941ea54775" />
</p>

<p align="center">
  <img width="536" height="468" alt="image" src="https://github.com/user-attachments/assets/a10680fa-17a7-4ea8-bf4e-241602af062d" />
  <img width="736" height="402" alt="image" src="https://github.com/user-attachments/assets/a620d1cd-426d-44f3-9d6b-efae6325a8bc" />
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
  <img width="1025" height="320" alt="image" src="https://github.com/user-attachments/assets/0cdaa5bb-9125-49b7-8f68-ed3fc5dd6f5d" />
  <img width="635" height="692" alt="image" src="https://github.com/user-attachments/assets/00739417-93b5-4d38-9ffa-6bb1995a7545" />
</p>
<p>
In Active Directory Users and Computers (ADUC), two Organizational Units (OUs) named _EMPLOYEES and _ADMINS are created to keep accounts organized. An admin account, jane_admin, is also added to the Domain Admins group to manage the domain securely.
</p>
<br />

<h3>Step 5. Joining Client-1 to the Domain</h3>
<p>
  <img width="580" height="473" alt="image" src="https://github.com/user-attachments/assets/23d6c56c-1382-4373-99ec-a8540676cd74" />
  <img width="1633" height="872" alt="image" src="https://github.com/user-attachments/assets/96c05751-66b3-4fea-949c-98875cae2918" />
  <img width="1027" height="679" alt="image" src="https://github.com/user-attachments/assets/f5a5b9c9-a944-4cdc-aa80-4b0b50c5033c" />
</p>
<p>
The client-1 virtual machine is joined to the mydomain.com domain through System Properties, confirming successful communication with the domain controller. In Active Directory Users and Computers (ADUC) on dc-1, the client-1 computer appears under the domain. This step confirms that the domain controller and DNS are working correctly between the two virtual machines (VMs), allowing the client to log in with domain accounts.
</p>
<br />

<h3>Step 6. <img align="center" alt="PowerShell Icon" width="20px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/powershell-colored.svg" /> PowerShell Bulk User Creation</h3>
<p>
  <img width="802" height="1037" alt="image" src="https://github.com/user-attachments/assets/7c42ead9-939e-4e05-bb22-f0cb5f7a8756" />
  <img width="832" height="1039" alt="image" src="https://github.com/user-attachments/assets/0e69d5bb-f8e3-4de0-8245-bfda48942538" />
</p>
<p>
In PowerShell ISE, the Generate-Names-Create-Users.ps1 script automatically creates 10,000 new user accounts in Active Directory. The _EMPLOYEES Organizational Unit (OU) in Active Directory Users and Computers (ADUC) shows the new users. This shows how PowerShell can save time by automating repetitive account creation tasks in Active Directory.
</p>
<br />

<h3>Step 7. Remote Desktop Access Test</h3>
<p>
  <img width="395" height="244" alt="image" src="https://github.com/user-attachments/assets/11bb44e5-c652-4154-84d3-d649218cafe5" />
  <img width="796" height="514" alt="image" src="https://github.com/user-attachments/assets/c0cd9b5d-dfc1-47f7-b2b8-65e99961ae22" />
  <img width="662" height="686" alt="image" src="https://github.com/user-attachments/assets/4ee6faba-a4ed-4aef-8a06-80fbb0243108" />
</p>
<p>
A Remote Desktop Protocol (RDP) login test is done using one of the new employee non-administrative domain user accounts. Successful login confirms that domain authentication and permissions are working correctly for normal users.
</p>
<br />

<h2>Conclusion</h2>
<p>
This project demonstrates how to set up and manage Active Directory Domain Services (AD DS) in the cloud using Microsoft Azure and PowerShell. It walks through creating and configuring a domain controller, setting up Organizational Units (OUs) and admin accounts, joining client computers to the domain, and using automation to bulk create user accounts using PowerShell, all while using Remote Desktop (RDP) for access. These steps build real-world skills in domain management, authentication, networking, and automation. The lab also highlights how cloud-based environments can be used to practice enterprise IT setups safely and efficiently.
</p>
<br />

<h2>Thank you for checking out my project!</h2>
<p>If you found it helpful or interesting, subscribe to my YouTube channel and 🔗connect with me on LinkedIn by clicking below:
</p>

[<img align="left" alt="Jeramy | YouTube" width="22px" src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/youtube.svg" />][youtube]
[<img align="left" alt="Jeramy | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" />][linkedin]
<br clear="left"/>

[youtube]: https://youtube.com/@jeramycanals
[linkedin]: https://linkedin.com/in/jeramycanals
