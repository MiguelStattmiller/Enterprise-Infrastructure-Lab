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
        LAN 192.168.20.0/24
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

![System Overview](Screenshots/04-pfSense-Console-Overview.png)

---

# System Information

The following screenshot shows the deployed firewall version and hardware information.

![System Information](Screenshots/05-System-Information.png)

---

# Network Interfaces

Two interfaces were configured.

| Interface | IP Assignment | Purpose |
|------------|--------------|---------|
| WAN | DHCP | Internet connectivity |
| LAN | Static | Enterprise internal network |

![Interfaces](Screenshots/06-Network-Interfaces.png)

---

# WAN Configuration

Configuration:

- DHCP IPv4
- Bridged Adapter
- Internet-facing interface
- OpenVPN endpoint

Responsibilities:

- Internet connectivity
- Incoming VPN connections
- External traffic filtering

---

# LAN Configuration

Configuration:

- Static IPv4 network
- Enterprise gateway
- Default gateway for all internal systems

Responsibilities:

- Internal routing
- Internet access through NAT
- Communication with Windows Server, Ubuntu Server and Windows Client

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

![WAN Rules](Screenshots/08-WAN-Firewall-Rules.png)

---

## LAN

Internal clients are allowed outbound connectivity.

| Action | Source | Destination | Purpose |
|---------|--------|-------------|---------|
| Allow | LAN | Any | Internet access |
| Anti-Lockout | LAN | Firewall | Web Management |

![LAN Rules](Screenshots/09-LAN-Firewall-Rules.png)

---

# Certificate Authority

An internal Certificate Authority (CA) was created for OpenVPN certificate authentication.

Purpose:

- Issue VPN certificates
- Authenticate VPN clients
- Manage certificate trust

![Certificate Authority](Screenshots/07-Certificate-Authority.png)

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

# Next Steps

The following integrations will be documented in subsequent sections of the Enterprise Infrastructure Lab:

- Windows Server integration
- Active Directory authentication
- DNS forwarding
- DHCP relay
- Wazuh monitoring
- Security event forwarding

---


