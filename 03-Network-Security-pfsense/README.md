# pfSense Firewall

## Overview

This section documents the deployment and configuration of **pfSense Community Edition** as the perimeter firewall for the Enterprise Infrastructure Lab.

The objective is to simulate a small enterprise environment by implementing secure network connectivity, traffic filtering, network segmentation and remote administration using industry-standard firewall practices.

---

## Objectives

- Deploy pfSense Community Edition as the perimeter firewall
- Configure WAN and LAN interfaces
- Configure IPv4 networking
- Implement firewall rules
- Configure OpenVPN remote access
- Create an internal Certificate Authority (CA)
- Deploy Squid Proxy
- Configure SquidGuard URL filtering
- Deploy Snort IDS/IPS
- Document the complete firewall configuration

---

## Technologies

- pfSense Community Edition
- UTM Virtualization

---


## pfSense Architecture

```text
                    Internet
                        │
                 WAN (Bridged)
                        │
              +------------------+
              |     pfSense      |
              | Firewall/Gateway |
              +------------------+
                        │
                 LAN (Host-Only)
                        │
          Enterprise Infrastructure Lab
```

---

## Configuration Sections

- VM Installation and Configuration
- WAN Interface Configuration
- LAN Interface Configuration
- Firewall Rules
- Certificate Authority
- OpenVPN
- Squid Proxy
- SquidGuard
- Snort IDS/IPS

---

## Folder Structure

```text
03-Network-Security-pfSense/
├── README.md
├── Screenshots/
├── configs/
│   ├── VM-Configuration.md
│   ├── pfSense-Configuration.md
│   ├── Firewall-Rules.md
│   ├── OpenVPN.md
│   ├── Snort.md
│   └── Squid.md
├── backups/
└── exports/
```

---


