# Active-Directory-Lab
Windows Server 2022 Active Directory Home Lab with a Windows 11 virtual machine using VirtualBox.

This project documents the steps I took to build a simple Active Directory lab environment using Windows Server 2022 and a Windows 11 client. Everything was set up in VirtualBox. The purpose of this lab was to get hands‑on practice with installing Active Directory, creating users and groups, and joining a client to the domain.

# Lab Overview 

Domain: ADL.local  
Domain Controller: Windows Server 2022  
Client Machine: Windows 11  
Hypervisor: VirtualBox  

---

## Repository Structure

Below is the full folder tree of all screenshots used in this project.  
Each folder name is also **clickable** for easy navigation.

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

---

## 1. Environment Setup (VirtualBox)

I started by creating two virtual machines: one for Windows Server 2022 and one for Windows 11.  
I configured VirtualBox networking so both machines were on the same internal network and could communicate with each other.

Screenshots: [01‑Environment‑Setup](Screenshots/1-VirtualBox-Set-up/)

---

## 2. Installing and Configuring Windows Server 2022

After installing Server 2022, I renamed the machine to `DC01`, set a static IP address, and pointed DNS to the server itself. This prepares it for the Active Directory Domain Services role.

Screenshots: [02‑Server‑Install‑and‑Config](Screenshots/2-Installing-Windows-Server2022/)

---

## 3. Installing Active Directory Domain Services

I added the AD DS role through Server Manager and promoted the server to a domain controller.  
I created a new forest called `lab.local` and rebooted once the setup completed.

Screenshots: [03‑AD‑DS‑Installation](Screenshots/4-Install-AD/)

---

## 4. Creating OUs, Users, and Groups

Using Active Directory Users and Computers, I created a basic OU structure and added a few test users and groups. This helped organize the domain and made it easier to apply Group Policy later.

Screenshots: [04‑OUs‑Users‑and‑Groups](Screenshots/6-Creating-OU-USERS-GROUPS/)

---

## 5. Setting Up the Windows 11 Client

I installed Windows 11, renamed the machine, and set the DNS server to the IP address of the domain controller. This is required before joining the domain.

Screenshots: [05‑Windows11‑Client‑Setup](Screenshots/5-Create-Domain/)

---

## 6. Joining the Client to the Domain

Once the client could ping the domain controller, I joined it to `lab.local`.  
After a reboot, I was able to log in using one of the domain accounts I created earlier.

Screenshots: [06‑Join‑Client‑to‑Domain](Screenshots/7-Add-to-domain/)

---

## 7. Group Policy Testing

To test Group Policy, I created a new GPO and linked it to one of my OUs.  
I tried out a few basic settings such as restricting access to the Control Panel and setting a desktop wallpaper.

Screenshots: [07‑Group‑Policy‑Examples](Screenshots/7-Add-to-domain/)

---

## 8. Testing and Troubleshooting

I tested logins, DNS resolution, and GPO application.  
Along the way, I fixed a few common issues such as incorrect DNS settings and time synchronization problems.

Screenshots: [08‑Testing‑and‑Troubleshooting](Screenshots/8-Log-in-domain-user/)

---

## What I Learned

- How to install and configure Active Directory  
- How DNS works within a domain environment  
- How to organize users and computers using OUs  
- How to join a Windows client to a domain  
- How Group Policy affects users and machines  
- How to troubleshoot common domain issues  

---

## Future Improvements

- Add a file server and test NTFS permissions  
- Deploy software using Group Policy  
- Automate user creation with PowerShell  
- Add more clients or additional server roles  
