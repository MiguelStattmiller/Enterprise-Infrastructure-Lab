# pfSense Community Edition - Configuration

This document describes the configuration implemented on **pfSense Community Edition 2.7.2** as the perimeter firewall and network gateway for the Enterprise Infrastructure Lab.

---

# Architecture

The firewall is positioned between the Internet and the isolated enterprise network.

```text
              Internet
                  │
            WAN (DHCP)
                  │
        +------------------+
        |     pfSense      |
        | Firewall/Gateway |
        +------------------+
                  │
                 LAN 
                  │
        Enterprise Lab Network
```

Main responsibilities:

- Internet gateway
- Stateful firewall
- Network Address Translation (NAT)
- OpenVPN Remote Access
- Certificate Authority
- Squid Proxy
- SquidGuard URL Filtering
- Snort IDS/IPS

---

# System Overview

The firewall was successfully deployed using **pfSense Community Edition 2.7.2** on a dedicated virtual machine hosted in **UTM for macOS**.

![System Overview](../Screenshots/04-pfSense-Console-Overview.png)

---

# System Information

The following screenshot shows the deployed firewall version and hardware information.

![System Information](../Screenshots/05-System-Information.png)

---

# Network Interfaces

Two interfaces were configured.

| Interface | IP Assignment | Purpose |
|------------|--------------|---------|
| WAN | DHCP | Internet connectivity |
| LAN | Static | Enterprise internal network |

![Network Interfaces](../Screenshots/06-Network-Interfaces.png)

---

## WAN Configuration

The WAN interface is configured in **DHCP mode** using a **Bridged Adapter**, allowing the firewall to obtain an IPv4 address from the external network.

Configuration:

- IPv4 Configuration: DHCP
- IPv6: Disabled
- Network Adapter: Bridged
- Interface: WAN
- Purpose: Internet connectivity

---

## LAN Configuration

The LAN interface provides the internal enterprise network used by the laboratory virtual machines.

Configuration:

- DHCP Server: Disabled (provided by Windows Server)
- IPv6: Disabled
- Default Gateway for internal hosts

---

# IPv6

IPv6 was intentionally disabled across the laboratory to simplify the environment and focus on IPv4 enterprise networking.

---

# Firewall Rules

## WAN

Only the OpenVPN service is exposed externally.

| Action | Protocol | Port | Purpose |
|---------|----------|------|---------|
| Allow | UDP | 1194 | OpenVPN |
| Block | Any | Any | Default deny |

![WAN Firewall Rules](../Screenshots/08-WAN-Firewall-Rules.png)

---

## LAN

Internal clients are allowed outbound connectivity.

| Action | Source | Destination | Purpose |
|---------|--------|-------------|---------|
| Allow | LAN | Any | Internet access |
| Anti-Lockout | LAN | Firewall | Web Management |

![LAN Firewall Rules](../Screenshots/09-LAN-firewall-Rules.png)

---

# Certificate Authority

An internal Certificate Authority (CA) was created for OpenVPN certificate authentication.

Purpose:

- Issue VPN certificates
- Authenticate VPN clients
- Manage certificate trust

![Certificate Authority](../Screenshots/07-Certificate-Authority.png)

---

# OpenVPN

OpenVPN provides secure remote access to the Enterprise Infrastructure Lab.

Configuration highlights:

- UDP Transport
- Certificate Authentication
- Dedicated VPN Tunnel
- Firewall Integration

---

# Proxy Services

## Squid

Installed and configured to provide:

- HTTP/HTTPS Proxy
- Web Caching
- Traffic Optimization

## SquidGuard

Configured for:

- URL Filtering
- Website Categorization
- Access Policies

---

# Snort IDS/IPS

Snort is deployed as the network Intrusion Detection and Prevention System.

Current capabilities:

- Network intrusion detection
- Rule-based inspection
- Traffic analysis
- Security event generation

---

# Configuration Highlights

| Feature | Status |
|----------|--------|
| WAN Interface | ✅ Configured |
| LAN Interface | ✅ Configured |
| NAT | ✅ Enabled |
| Firewall | ✅ Configured |
| OpenVPN | ✅ Operational |
| Certificate Authority | ✅ Created |
| Squid | ✅ Installed |
| SquidGuard | ✅ Installed |
| Snort IDS/IPS | ✅ Installed |
| IPv6 | ❌ Disabled |

---



