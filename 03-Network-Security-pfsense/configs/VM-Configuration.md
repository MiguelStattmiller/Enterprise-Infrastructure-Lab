# pfSense Community Edition - Virtual Machine Configuration

This document describes the virtual machine configuration used to deploy **pfSense Community Edition** in the **Enterprise Infrastructure Lab**.

---

## Overview

pfSense is deployed as the **firewall and network gateway** for the lab environment.

The virtual machine was deployed using **UTM** on **macOS** as part of a virtual enterprise infrastructure.

The VM uses two network interfaces:

- **WAN** – Bridged network providing external/Internet connectivity.
- **LAN** – Host Only network providing an isolated internal lab environment.

---

## VM Summary

| Parameter | Configuration |
|------------|---------------|
| Virtual Machine Name | Pfsense - CIBER |
| Hypervisor | UTM |
| Operating System | pfSense Community Edition |
| Installation Media | pfSense CE ISO |
| Architecture | x86_64 |
| Machine Type | Standard PC (Q35 + ICH9, 2009) |
| Memory | 4 GB |
| CPU Cores | 3 |
| Disk Size | 6.09 GB |
| Network Card Model | Intel Gigabit Ethernet (e1000) |

---

## Network Configuration

| Adapter | Purpose | Network Mode | Interface | Network Card |
|---------|---------|--------------|-----------|--------------|
| Adapter 1 | WAN | Bridged (Advanced) | Wi-Fi (en0) | Intel Gigabit Ethernet (e1000) | 
| Adapter 2 | LAN | Host Only | Default (private) | Intel Gigabit Ethernet (e1000) | 

---

## Network Design

```text
                 Internet
                     │
               Wi-Fi (en0)
                     │
              WAN (Bridged)
                     │
              +---------------+
              |    pfSense    |
              +---------------+
                     │
              LAN (Host Only)
                     │
          Internal Lab Network
             ┌──────────────┐
             │              │
      Windows Server   Ubuntu Desktop
                         (Wazuh SIEM)
```

---

## Purpose

This virtual machine provides the network perimeter for the **Enterprise Infrastructure Lab** and will be used throughout the project to configure:

- Firewall Rules
- VPN
- Network Routing
- Traffic Monitoring
- Secure Network Segmentation

---

## Screenshots

### System Configuration

The following screenshot shows the hardware configuration used to deploy the pfSense virtual machine.

![System Configuration](Screenshots/01-System-Configuration.png)

---

### WAN Network Adapter

The WAN interface is configured in **Bridged (Advanced)** mode using the host's Wi-Fi interface (`en0`). This allows pfSense to communicate with the external network and simulate Internet connectivity.

![WAN Network Adapter](Screenshots/02-WAN-Network-Adapter.png)

---

### LAN Network Adapter

The LAN interface is configured in **Host Only** mode to provide an isolated internal network for the Enterprise Infrastructure Lab.

![LAN Network Adapter](Screenshots/03-LAN-Network-Adapter.png)

---
