# Active-Directory-Lab-PowerShell-Remoting
Enterprise-style Active Directory lab with DNS configuration and PowerShell Remoting using VMware
# 🖥️ Active Directory Lab with PowerShell Remoting

## 📌 Overview

This project demonstrates the setup of an enterprise-style Active Directory environment using VMware. It includes a Domain Controller and a Windows client machine configured within the same domain (`lab.local`).

PowerShell Remoting (WinRM) is implemented to enable remote command execution between systems.

---

## 🛠️ Technologies Used

* VMware Workstation
* Windows Server (Domain Controller)
* Windows 10 Client
* Active Directory Domain Services (AD DS)
* DNS Configuration
* PowerShell (WinRM)

---

## ⚙️ Lab Setup

### 🔹 Network Configuration

* Host-only network (VMnet1)
* Static IP addressing

  * Domain Controller: 192.168.12.10
  * Client: 192.168.12.20

### 🔹 Active Directory

* Domain created: `lab.local`
* Client machine joined to domain

---

## 🔐 PowerShell Remoting

### Enable Remoting (Client)

```powershell
Enable-PSRemoting -Force
```

### Remote Session (from DC)

```powershell
Enter-PSSession -ComputerName CLIENT.lab.local
```

---

## 🧪 Example Commands

```powershell
Get-Service spooler
New-Item -Path C:\hackedyou -ItemType Directory
```

---

## 🐞 Troubleshooting

### Issue: Domain Join Failure

* Cause: Incorrect DNS configuration
* Fix: Set DNS to Domain Controller IP

### Issue: Authentication Errors

* Cause: Multiple IP addresses (NAT + Host-only conflict)
* Fix: Removed incorrect IP (192.168.137.x)

---

## 📸 Screenshots

(Add screenshots in /screenshots folder)

---

## 🧠 Key Learnings

* Importance of DNS in Active Directory
* Kerberos vs NTLM authentication
* PowerShell Remoting for remote administration
* Real-world troubleshooting of network issues

---

## 🚀 Future Improvements

* Add multiple clients      
* Implement Group Policies (GPO)
* Simulate cybersecurity attacks (lateral movement)

---
