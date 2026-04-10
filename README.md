# 🖥️ Active Directory Lab with PowerShell Remoting

## 📌 Overview

This project demonstrates an enterprise-style Active Directory lab setup using VMware, including DNS configuration and PowerShell Remoting for remote system administration.

---

## 🎯 Objectives

* Configure an Active Directory Domain Controller (AD-DC)
* Join a client machine to the domain (`lab.local`)
* Configure DNS for domain communication
* Enable and use PowerShell Remoting
* Execute commands remotely across machines

---

## 🛠️ Lab Setup

| Component         | Details            |
| ----------------- | ------------------ |
| Hypervisor        | VMware             |
| Domain Controller | Windows Server     |
| Client Machine    | Windows 10         |
| Domain            | lab.local          |
| Network           | Host-only (VMnet1) |

---

## 🌐 Network Configuration

* AD-DC IP: `192.168.12.10`
* Client IP: `192.168.12.20`
* DNS: Pointed to Domain Controller

---

## 🔐 PowerShell Remoting Setup

### Enable Remoting

```powershell
Enable-PSRemoting -Force
```

### Test Connectivity

```powershell
Test-WSMan 192.168.12.20
```

### Remote Command Execution

```powershell
Invoke-Command -ComputerName 192.168.12.20 -ScriptBlock { hostname }
```

---

## 💻 Example: Remote Task Execution

```powershell
Invoke-Command -ComputerName 192.168.12.20 `
-FilePath "C:\Users\Administrator\admin_tasks.ps1" `
-Credential lab\Administrator
```

✔ Successfully created directory remotely on client machine.

---

## 📸 Screenshots

### 🔹 Successful Remote Command

![PS Remoting](screenshots/ps-remoting-success.png)

### 🔹 Folder Created on Client

![Folder Created](screenshots/folder-created.png)

---

## 🧠 Key Learnings

* Active Directory Domain setup
* DNS configuration and troubleshooting
* PowerShell Remoting (WinRM)
* Kerberos authentication issues & fixes
* Remote command execution
* Basic lateral movement simulation

---

## ⚠️ Troubleshooting Highlights

* Fixed DNS resolution issues (`nslookup`)
* Resolved Kerberos authentication errors
* Configured TrustedHosts when needed
* Ensured time synchronization between machines

---

## 🚀 Future Improvements

* Automate user creation via PowerShell
* Implement Group Policy Objects (GPO)
* Add multiple client machines for scaling
* Integrate security monitoring (Event Logs / SIEM)

---

## 👨‍💻 Author

**Eshaan Pilar**

---
