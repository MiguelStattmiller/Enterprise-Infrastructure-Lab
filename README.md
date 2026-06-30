# Enterprise-Infrastructure-Lab

<div align="center">

# 🏗️ Enterprise Infrastructure & Security Lab

### Systems Integration • Networking • Cybersecurity • Infrastructure Engineering

[![pfSense](https://img.shields.io/badge/pfSense-Firewall-orange?style=for-the-badge)]
[![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-blue?style=for-the-badge)]
[![Windows Server](https://img.shields.io/badge/Windows_Server-AD/DNS/DHCP-0078D6?style=for-the-badge)]
[![Ubuntu](https://img.shields.io/badge/Ubuntu_Server-Linux-E95420?style=for-the-badge)]
[![Docker](https://img.shields.io/badge/Docker-Containers-2496ED?style=for-the-badge)]
[![Python](https://img.shields.io/badge/Python-Automation-3776AB?style=for-the-badge)]

---

Design, deployment and documentation of a complete enterprise infrastructure laboratory focused on **Systems Integration**, **Networking**, **Cybersecurity** and **Infrastructure Engineering**.

</div>

---

# 📖 Project Overview

This laboratory simulates a small enterprise infrastructure where multiple technologies are integrated into a secure and scalable environment.

The project focuses on understanding not only **how** technologies work individually, but also **how they interact together** inside a production-like infrastructure.

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
```

---

# 📈 Skills Demonstrated

- Systems Integration
- Systems Engineering
- Network Design
- Infrastructure Deployment
- Cybersecurity
- Network Security
- Windows Administration
- Linux Administration
- SIEM Deployment
- Infrastructure Troubleshooting
- Python Automation

---

# 🚀 Future Improvements

- Azure Integration
- Microsoft Entra ID
- PowerShell Automation
- Infrastructure as Code
- Backup & Disaster Recovery
- Monitoring Dashboard
- Enterprise VPN
- Multi-site Network

---

## 👨‍💻 Author

**Miguel Stattmiller Albuquerque**

Electrical Engineer • Systems Integration • Networks & Cybersecurity

[LinkedIn](https://linkedin.com/in/miguel-stattmiller-albuquerque)
