# Homelab Networking (Phase 2)


## Overview 
This repository documents the networking design and implementation of my homelab environment. The goal is to build a scalable and secure network that evolves from a simple apartment-based setup into a segmented, enterprise-style infrastructure.

--- 

## Current Network Architecture (Phase 1)
The current network is designed around limited physical infrastructure and relies on a Raspberry Pi 4 to act as a router.

### Design 
- ISP router provides internet via WiFi
- Raspberry Pi 4 connects to ISP WiFi (WAN)
- Raspberry Pi 4 provides Ethernet LAN to internal systems
- Proxmox server connects directly to the Pi via Ethernet
- All devices operate within a single flat network

### Diagram
--- Add Diagrams ---- 

---

## Why not Pfsense or OPNsense
I choose Ubuntu Server as my router instead of Pfsense or OPNsense, one reason is because Raspberry Pi 4 uses arm based chip instead of an x86 chip, but the main reason is to gain a deeper understanding of networking fundamentals.

Using Ubuntu Server allows for  
 - Full control over network configuration
 - Hands-on experience with tools like netplan, iptables, routing tables, and linux cli
 - A better understanding of how networking works at a low-level
 - Low power draw due to no gui
 - Easy to ingrate my own python scripts for automation

This approach allows me to understanding networking without using pre-configuration applications like (Pfsense, OPNsense, OpenWRT) and aligns with my goals for working towards my CCNA.

--- 

## Current configuration
### Raspberry Pi 4 (Router)
- OS: Ubuntu Server
- WAN Interface: WiFi (connected to ISP router)
- LAN Interface: Ethernet
- Functions:
  - NAT (internet sharing)
  - DHCP (Local IP assignment)
  - Basic routing

### Proxmox Server
- Connected via Ethernet to Pi
- Host virtual machines
- Uses Pi as default gateway

### VLAN configuration
---- Adding VLAN configuration soon ---- 

### Current Limitations
- No VLAN segmentation (flat network)
- No managed switch
- Limited traffic isolation
- WiFi uplink may introduce instability
- No dedicated firewall rules per network segment

--- 

## Troubleshooting
Example issue: No internet connectivity (VM)

---

## Lesson Learned
- Proper gateway configuration is critical for connectivity
- NAT routing enables internet access in isolated environments
- Flat networks are simple but lack security and scalability
- Structured troubleshooting improves efficiency

---

## Future Networking Plans (Phase 2)
---- Currently working this ----
