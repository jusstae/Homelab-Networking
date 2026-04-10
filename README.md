# Homelab Networking

## Overview 
This repo documents the networking design, configuration, and troubleshooting within my homelab environment.

This goal is to simulate real-world network infrastructure by implementing routing, VLAN segmentation, and structured troubleshooting.

--- 

## Network Architecture
Network diagram

--- 

## Architecture Explanation 
- The ISP modem provides WAN connectivity over WiFi
- The Raspberry Pi 4 functions as a router, bridging WAN (WiFi) to LAN (Ethernet)
- The Proxmox server connects via Ethernet and hosts virtual machines
- A VLAN-aware Linux bridge (vmbr0) is used to segment network traffic

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

## VLAN Configuration 






