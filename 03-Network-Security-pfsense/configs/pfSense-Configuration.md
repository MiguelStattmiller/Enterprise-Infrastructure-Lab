# pfSense Community Edition - Configuration

This document describes the configuration performed on **pfSense Community Edition** for the **Enterprise Infrastructure Lab**.

---

## Overview

pfSense is deployed as the **perimeter firewall and network gateway** of the Enterprise Infrastructure Lab.

The firewall is responsible for controlling traffic between the Internet and the internal enterprise network while providing secure remote access and network security services.

The configuration includes:

- WAN and LAN interfaces
- Stateful Firewall
- NAT
- OpenVPN Remote Access
- Certificate Authority (CA)
- Squid Proxy
- SquidGuard URL Filtering
- Snort IDS/IPS
- IPv6 disabled

Unlike traditional pfSense deployments, **DNS**, **DHCP**, **Active Directory**, and **Group Policy Objects (GPOs)** are provided by the **Windows Server**, while pfSense operates strictly as the network gateway and security appliance.

---

## System Overview

The pfSense firewall was successfully deployed and initialized with dedicated WAN and LAN interfaces.

![pfSense Console](../Screenshots/04-pfSense-Console-Overview.png)

---

## System Information

The firewall is running **pfSense Community Edition 2.7.2** on a virtual machine hosted in **UTM for macOS**.

![System Information](../Screenshots/05-System-Information.png)

---

## Network Interfaces

Two interfaces were configured.

| Interface | Purpose |
|-----------|----------|
| WAN | External network connectivity (Bridged Adapter) |
| LAN | Internal enterprise network |

![Network Interfaces](../Screenshots/06-Network-Interfaces.png)

---

## WAN Configuration

The WAN interface receives its IPv4 configuration through DHCP from the external network.

Its primary functions are:

- Internet connectivity
- OpenVPN endpoint
- External firewall protection

---

## LAN Configuration

The LAN interface provides connectivity for the internal enterprise infrastructure.

The Windows Server uses this interface as its default gateway.

Responsibilities include:

- Internal routing
- Gateway services
- Access to external networks

---

## IPv6 Configuration

IPv6 was intentionally disabled across the laboratory.

This simplifies the environment, keeps the project focused on IPv4 enterprise networking, and reduces unnecessary attack surface.

---

## Firewall Rules

### WAN Rules

Only the OpenVPN service is exposed externally.

![WAN Firewall Rules](../Screenshots/08-WAN-Firewall-Rules.png)

---

### LAN Rules

LAN clients are allowed outbound connectivity while inbound Internet traffic remains blocked by default.

![LAN Firewall Rules](../Screenshots/09-LAN-firewall-Rules.png)

---

## Certificate Authority

An internal Certificate Authority (CA) was created for certificate-based VPN authentication.

The CA is responsible for:

- Issuing VPN certificates
- Authenticating VPN clients
- Managing certificate trust

![Certificate Authority](../Screenshots/07-Certificate-Authority.png)

---

## OpenVPN

OpenVPN provides encrypted remote access to the Enterprise Infrastructure Lab.

Configuration includes:

- UDP transport
- Certificate-based authentication
- Dedicated VPN tunnel
- Firewall integration

---

## Proxy Services

### Squid

Squid provides:

- HTTP/HTTPS proxy
- Web caching
- Traffic optimization

### SquidGuard

SquidGuard extends Squid with:

- URL filtering
- Website categorization
- Access control

---

## Snort IDS/IPS

Snort was deployed as the network Intrusion Detection and Prevention System.

It will later be integrated with Wazuh to demonstrate:

- Attack detection
- Alert generation
- Traffic blocking
- Centralized monitoring

---

## Services Summary

| Service | Purpose |
|---------|---------|
| Firewall | Traffic filtering |
| NAT | Internet access |
| OpenVPN | Secure remote access |
| CA | VPN certificates |
| Squid | Proxy server |
| SquidGuard | Web filtering |
| Snort | IDS/IPS |

Infrastructure services such as **Active Directory**, **DNS**, **DHCP**, and **Group Policy Objects** are hosted on the Windows Server.

---


