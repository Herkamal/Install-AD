<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

# Active Directory Installation in Azure

This lab demonstrates how to set up and configure Active Directory on a Windows Server virtual machine hosted in Microsoft Azure. It includes network configuration, static IP setup, DNS changes, and connectivity verification with a client system.

---

## 🧰 Tools & Technologies Used

- Microsoft Azure (Virtual Machine Hosting)
- Windows Server 2022 (Domain Controller)
- Windows 10 Pro 
- Remote Desktop Connection
- Active Directory Domain Services (AD DS)
- PowerShell & GUI tools

---

## 🎯 Objective

To configure an Active Directory infrastructure in Azure, including:

- Setting static IP addresses  
- Installing AD DS  
- Promoting the server to a domain controller  
- Adjusting firewall settings  
- Testing domain connectivity from a client machine

---

## 🖥️ Step-by-Step Setup

### 📂 1. Creating the Domain Controller (DC)

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/Creating.png?raw=true" width="80%"/>
</p>

A new Windows Server VM is created in Azure to serve as the Domain Controller. Initial setup includes assigning the proper virtual network and security group.

---

### 🌐 2. Setting a Static IP Address

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/static.png?raw=true" width="80%"/>
</p>

To ensure consistent domain functionality, a static private IP is assigned to the server through the Azure portal.

---

### ⚙️ 3. Verifying System Information

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/systemServer.png?raw=true" width="80%"/>
</p>

System properties are reviewed to confirm hostname and Windows edition, which are important for domain naming conventions and compatibility.

---

### 🛡️ 4. Opening Firewall for AD Services

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/run-firewall.png?raw=true" width="80%"/>
</p>

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/firewall-off.png?raw=true" width="80%"/>
</p>

Windows Defender Firewall settings are adjusted to allow necessary AD services to communicate. In this step, the firewall is turned off temporarily to ensure connectivity during setup.

---

### 🌍 5. Changing DNS Server on the Client

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/changing-dns-server.png?raw=true" width="80%"/>
</p>

The Windows 10 client VM is pointed to the Domain Controller's IP address as its primary DNS server to ensure proper domain resolution.

---

### 🔄 6. Restarting the Client VM

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/client-1-restart.png?raw=true" width="80%"/>
</p>

After setting the DNS server, the client machine is restarted to apply networking changes and prepare for domain join.

---

### 📡 7. Verifying Network Connection

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/ping.png?raw=true" width="80%"/>
</p>

Using the `ping` command, the client system checks communication with the Domain Controller to ensure connectivity and proper DNS resolution.

---

### 🔍 8. Checking IP Configuration

<p align="center">
  <img src="https://github.com/Herkamal/Install-AD/blob/main/ipconfig-all.png?raw=true" width="80%"/>
</p>

The `ipconfig /all` command confirms DNS settings and IP assignment. This step ensures that everything is correctly configured before joining the domain.

---

## ✅ Summary

This lab successfully set the foundation for an Active Directory environment in Azure. The configuration ensured that the Domain Controller and client VM could communicate securely, and the client was properly prepared to join the domain.

---

