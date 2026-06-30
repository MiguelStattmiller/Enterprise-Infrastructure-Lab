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

This project is part of my Enterprise Infrastructure Lab, a virtual environment fully built using **UTM** on macOS.

The lab consists of three virtual machines:

- **pfSense Community Edition** – Firewall and Network Gateway
- **Windows Server** – Active Directory and Infrastructure Services
- **Ubuntu Server** – Hosting the Wazuh SIEM platform

The objective is to simulate a small enterprise infrastructure by deploying secure networking, centralized identity management and security monitoring within an isolated virtual environment.

---

> [!NOTE]
> To protect personal information, all IP addresses, hostnames, MAC addresses and other network identifiers shown throughout this repository are used **for documentation purposes only**.
>
> Any values displayed in screenshots or configuration examples have been anonymized, modified or recreated and **do not represent my personal or home network**.

---

# 🎯 Objectives

- Design an enterprise network architecture
- Implement network segmentation using VLANs
- Deploy and configure pfSense Firewall
- Configure Windows Server infrastructure
- Implement Active Directory, DNS and DHCP
- Deploy Ubuntu Server services
- Implement SIEM monitoring using Wazuh
- Configure IDS/IPS with Snort
- Automate security tasks with Python
- Practice troubleshooting and systems integration

---

# 🏛️ Lab Architecture

```
                Internet
                    │
              ISP Router
                    │
             ┌────────────┐
             │  pfSense   │
             └────────────┘
                    │
          ┌─────────┴─────────┐
          │                   │
      Management VLAN     User VLAN
          │                   │
   Windows Server        Ubuntu Server
          │                   │
     Active Directory      Docker
          │                   │
      DNS / DHCP           Wazuh SIEM
          │                   │
     Windows Client      Linux Client

```

---

# ⚙️ Technologies

| Category | Technologies |
|----------|--------------|
| Networking | VLANs, Routing, NAT |
| Firewall | pfSense |
| IDS/IPS | Snort |
| SIEM | Wazuh |
| Virtualization | UTM, VMware |
| Windows Infrastructure | Active Directory, DNS, DHCP |
| Linux | Ubuntu Server |
| Containers | Docker |
| Security | Nmap |
| Automation | Python |

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



