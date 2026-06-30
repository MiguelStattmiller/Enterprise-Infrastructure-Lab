# pfSense Firewall

## Overview

This section documents the deployment and configuration of **pfSense Community Edition** as the perimeter firewall for the Enterprise Infrastructure Lab.

The objective is to simulate a small enterprise environment by implementing secure network connectivity, traffic filtering, network segmentation and remote administration using industry-standard firewall practices.

---

## Objectives

- Deploy pfSense as the network gateway
- Configure WAN and LAN interfaces
- Configure DHCP and DNS services
- Implement firewall rules following the principle of least privilege
- Configure Network Address Translation (NAT)
- Create and manage VLANs
- Configure secure remote access (VPN)
- Monitor firewall logs and traffic
- Document every configuration step

---

## Technologies

- pfSense Community Edition
- UTM Virtualization

---

## Lab Architecture

```
                    Internet
                        │
                        │
                 +---------------+
                 |    pfSense    |
                 +---------------+
                  │            │
             WAN  │            │ LAN
                  │            │
                  │       +-----------+
                  │       |  Switch   |
                  │       +-----------+
                  │        │    │    │
                  │        │    │    │
                  │     Windows Ubuntu Client
                  │      Server Server
```

---

## Procedures

- [ ] VM Installation and configuration
- [ ] pfSense Configuration
- [ ] WAN Configuration
- [ ] LAN Configuration
- [ ] Firewall Rules
- [ ] NAT Configuration
- [ ] VPN Configuration
- [ ] Port Forwarding
- [ ] Aliases
- [ ] Logging & Monitoring
- [ ] Backup & Restore

---

## Folder Structure

```
03-Network-Security-pfsense/
├── README.md
├── Screenshots/
├── Configs/
├── Firewall-rules/
├── Vlan/
├── Vpn/
└── Backups/
```

---


