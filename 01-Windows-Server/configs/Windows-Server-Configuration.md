# Windows Server 2022 - Configuration

This document describes the configuration implemented on **Microsoft Windows Server 2022 Datacenter Evaluation** for the Enterprise Infrastructure Lab.

---

# Active Directory Administrative Center

The Active Directory Administrative Center provides the modern administrative interface used to manage the Active Directory environment.

![Active Directory Administrative Center](../Screenshots/01-AD-Administrative-Center.png)

---

# Server Manager Dashboard

The Server Manager dashboard provides a centralized view of all installed roles and services running on the server.

Installed roles:

| Role | Purpose |
|------|---------|
| Active Directory Domain Services | Identity and authentication |
| DNS Server | Name resolution |
| DHCP Server | Dynamic IP allocation |
| File and Storage Services | Storage management |

![Server Manager](../Screenshots/02-SM-Dashboard.png)

---

# System Information

The following screenshot shows the deployed Windows Server version together with the hardware allocated to the virtual machine.

| Component | Value |
|-----------|-------|
| Operating System | Windows Server 2022 Datacenter Evaluation |
| Hostname | DC1 |

![System Information](../Screenshots/03-System-Information.png)

---

# Local Server Configuration

The Local Server console summarizes the core operating system configuration.

| Configuration | Status |
|--------------|--------|
| Hostname | Configured |
| Domain Membership | Joined |
| Windows Defender Firewall | Enabled |
| Remote Management | Enabled |
| Remote Desktop | Disabled |
| IPv4 Configuration | Static |
| Windows Defender Antivirus | Enabled |


![Local Server](../Screenshots/04-Local-Server.png)

---

# Windows Defender Firewall

Windows Defender Firewall provides the first layer of protection for the Windows Server.

| Feature | Status |
|---------|--------|
| Domain Profile | Enabled |
| Private Profile | Enabled |
| Public Profile | Enabled |
| Inbound Traffic | Restricted |
| Outbound Traffic | Allowed |
| Group Policy Management | Enabled |

![Windows Defender Firewall](../Screenshots/05-Windows-Defender.png)

---

# Active Directory Users and Computers

Active Directory Users and Computers (ADUC) provides the classic administrative interface used to manage the Active Directory objects.


![Active Directory Users and Computers](../Screenshots/06-AD-Users.png)

---

# DNS Server

The DNS Server is integrated with Active Directory and provides internal name resolution for the laboratory environment.

| Configuration | Status |
|--------------|--------|
| Active Directory Integrated Zone | Configured |
| Forward Lookup Zone | Configured |
| SOA Record | Present |
| NS Record | Present |
| Host (A) Records | Configured |
| Automatic Active Directory Registration | Enabled |

![DNS Manager](../Screenshots/07-DNS-Manager.png)

---

# DHCP Server

The DHCP Server automatically provides network configuration to all internal clients.

Scope configuration:

| Option | Purpose |
|---------|---------|
| Router | Default Gateway |
| DNS Server | Internal DNS Resolution |
| DNS Domain Name | Active Directory Domain |

![DHCP Server](../Screenshots/08-DHCP.png)

---

# Windows Server Roles Summary

| Role | Status |
|---------|--------|
| Active Directory Domain Services | ✅ Operational |
| Domain Controller | ✅ Operational |
| DNS Server | ✅ Operational |
| DHCP Server | ✅ Operational |
| Windows Defender Firewall | ✅ Enabled |
| File and Storage Services | ✅ Operational |
| Remote Management | ✅ Enabled |
| Remote Desktop | ❌ Disabled |

---

# Security Configuration

The Windows Server has been configured following basic security best practices.

Implemented security controls:

- Windows Defender Firewall enabled
- Windows Defender Antivirus enabled
- Static IP configuration
- Domain-based authentication
- Active Directory integrated DNS
- Centralized DHCP management
- Remote Desktop disabled
- Remote Management enabled

---
