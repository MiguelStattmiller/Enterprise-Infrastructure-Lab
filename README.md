# Enterprise-Infrastructure-Lab

<div align="center">

# 🏗️ Enterprise Infrastructure & Security Lab

### Systems Integration • Networking • Cybersecurity • Infrastructure Engineering

[![pfSense](https://img.shields.io/badge/pfSense-Firewall-orange?style=for-the-badge)]
[![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-blue?style=for-the-badge)]
[![Windows Server](https://img.shields.io/badge/Windows_Server-AD/DNS/DHCP-0078D6?style=for-the-badge)]
[![Ubuntu](https://img.shields.io/badge/Ubuntu_Server-Linux-E95420?style=for-the-badge)]
[![Docker](https://img.shields.io/badge/Docker-Containers-2496ED?style=for-the-badge)]


---

Design, deployment and documentation of a complete enterprise infrastructure laboratory focused on **Systems Integration**, **Networking**, **Cybersecurity** and **Infrastructure Engineering**.

</div>

---

## Project Overview

This project is part of my **Enterprise Infrastructure Lab**, a virtual enterprise environment built entirely using **UTM on macOS**.

The lab simulates a small enterprise network composed of three virtual machines:

- **pfSense Community Edition** – Enterprise firewall, network gateway, routing, NAT, DNS, DHCP, OpenVPN remote access, Snort IDS/IPS, Squid Proxy and SquidGuard web filtering.
- **Windows Server** – Active Directory Domain Services (AD DS), DNS, DHCP integration, Organizational Units (OUs), Group Policy Objects (GPOs), centralized authentication and enterprise infrastructure management.
- **Ubuntu Desktop** – Linux administration and deployment of the Wazuh SIEM platform for centralized log collection, monitoring and security event analysis.

The environment is intentionally configured as an **IPv4-only network**, with **IPv6 disabled** to reduce unnecessary complexity and maintain the focus on core enterprise infrastructure technologies. This approach simplifies the deployment of firewall policies, Active Directory, DNS, DHCP, VPN services and security monitoring without requiring parallel IPv6 configurations. IPv6 can be incorporated in future iterations of the lab as additional networking scenarios are developed.

The objective of this project is to simulate a realistic enterprise infrastructure by integrating secure networking, centralized identity management, endpoint administration and security monitoring within an isolated virtual environment.
---

> [!NOTE]
> For privacy and security reasons, sensitive network information such as IP addresses, MAC addresses, hostnames and other identifiers may be intentionally hidden or anonymized in screenshots and configuration examples.
>
> Any values shown are for documentation purposes only and do **not** represent my personal or home network.

---

# 🎯 Objectives

- Design an enterprise network architecture
- Deploy and configure pfSense Firewall
- Configure Windows Server infrastructure
- Implement Active Directory, DNS and DHCP
- Deploy Ubuntu Server services
- Implement SIEM monitoring using Wazuh
- Configure IDS/IPS with Snort
- Practice troubleshooting and systems integration

---

## Lab Architecture

```text
                                        Internet
                                            │
                                            │
                                    WAN (Bridged)
                                            │
                                    +----------------+
                                    |    pfSense     |
                                    | Firewall/GW    |
                                    +----------------+
                                            │
                                    LAN (Host-Only)
                                            │
        ┌───────────────────────────┼───────────────────────────┐
        │                           │                           │
        │                           │                           │
+--------------------+     +--------------------+     +--------------------+
|   Windows Server   |     |   Ubuntu Server    |     |  Windows Client    |
|--------------------|     |--------------------|     |--------------------|
| Active Directory   |     | Wazuh SIEM         |     | Domain Joined      |
| DNS Server         |     | Dashboard          |     | Enterprise Client  |
| DHCP Server        |     | Indexer            |     | GPO Applied        |
| Group Policies     |     | Manager            |     |                    |
+--------------------+     +--------------------+     +--------------------+
```

---

# ⚙️ Technologies

| Category | Technologies |
|----------|--------------|
| Firewall | pfSense |
| IDS/IPS | Snort |
| SIEM | Wazuh |
| Virtualization | UTM |
| Windows Infrastructure | Active Directory, DNS, DHCP |
| Linux | Ubuntu Server |
| Containers | Docker |
| Security | Nmap |

---

# 📂 Repository Structure

```
01-network-design/
02-virtualization/
03-pfsense-firewall/
04-windows-server/
05-linux-server/
06-wazuh-siem/
07-snort/
08-security-testing/
09-python-automation/
10-documentation/



