# Active-Directory-Lab
Windows Server 2022 Active Directory Home Lab with a Windows 11 virtual machine using VirtualBox.

This project documents the steps I took to build a simple Active Directory lab environment using Windows Server 2022 and a Windows 11 client. Everything was set up in VirtualBox. The purpose of this lab was to get hands‑on practice with installing Active Directory, creating users and groups, and joining a client to the domain.

# Lab Overview 

Domain: ADL.local  
Domain Controller: Windows Server 2022  
Client Machine: Windows 11  
Hypervisor: Oracle VirtualBox  



## Repository Structure

Below is the full folder tree of all screenshots used in this project.  
Each folder name is also clickable for easy navigation.

```
Screenshots
├── 1-VirtualBox-Set-up
├── 2-Installing-Windows-Server2022
├── 3-Static-IP
├── 4-Install-AD
├── 5-Create-Domain
├── 6-Creating-OU-USERS-GROUPS
├── 7-Add-to-domain
└── 8-Log-in-domain-user
```

### Clickable Folder Links

- [1‑VirtualBox‑Set‑up](Screenshots/1-VirtualBox-Set-up/)
- [2‑Installing‑Windows‑Server2022](Screenshots/2-Installing-Windows-Server2022/)
- [3‑Static‑IP](Screenshots/3-Static-IP/)
- [4‑Install‑AD](Screenshots/4-Install-AD/)
- [5‑Create‑Domain](Screenshots/5-Create-Domain/)
- [6‑Creating‑OU‑USERS‑GROUPS](Screenshots/6-Creating-OU-USERS-GROUPS/)
- [7‑Add‑to‑domain](Screenshots/7-Add-to-domain/)
- [8‑Log‑in‑domain‑user](Screenshots/8-Log-in-domain-user/)



## 1. Environment Setup (VirtualBox)

I started by creating two virtual machines: one for Windows Server 2022 and one for Windows 11.  
I configured VirtualBox networking so both machines were on the same internal network and could communicate with each other.

Screenshots: [1‑VirtualBox‑Set‑up](Screenshots/1-VirtualBox-Set-up/)



## 2. Installing Windows Server 2022

I installed Windows Server 2022, configured basic settings, and prepared the machine for domain controller promotion.

Screenshots: [2‑Installing‑Windows‑Server2022](Screenshots/2-Installing-Windows-Server2022/)



## 3. Setting a Static IP Address

Before installing Active Directory, I configured a static IP address on the server.  
This ensures stable DNS and domain controller functionality.

Screenshots: [3‑Static‑IP](Screenshots/3-Static-IP/)



## 4. Installing Active Directory Domain Services (AD DS)

I added the AD DS role through Server Manager.  
This installs the necessary components to promote the server to a domain controller.

Screenshots: [4‑Install‑AD](Screenshots/4-Install-AD/)



## 5. Creating the Domain (ADL.local)

I promoted the server to a domain controller and created a new directory: ADL.local.  
After the installation, the server rebooted and became the primary domain controller.

Screenshots: [5‑Create‑Domain](Screenshots/5-Create-Domain/)



## 6. Creating OUs, Users, and Groups

Using Active Directory Users and Computers, I created:

- Organizational Units (OUs)  
- User accounts  
- User groups  

This helps organize the domain and prepares for Group Policy.

Screenshots: [6‑Creating‑OU‑USERS‑GROUPS](Screenshots/6-Creating-OU-USERS-GROUPS/)



## 7. Joining the Windows 11 Client to the Domain

I configured the Windows 11 client to use the domain controller as its DNS server.  
Once it could resolve the domain, I joined it to ADL.local and logged in using a domain account.

Screenshots: [7‑Add‑to‑domain](Screenshots/7-Add-to-domain/)



## 8. Logging in as a Domain User

Finally, I tested domain authentication by logging into the Windows 11 client using one of the domain accounts created earlier.

Screenshots: [8‑Log‑in‑domain‑user](Screenshots/8-Log-in-domain-user/)



## What I Learned

- How to install and configure Active Directory  
- How DNS works within a domain environment  
- How to organize users and computers using OUs  
- How to join a Windows client to a domain  
