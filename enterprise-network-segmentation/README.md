Enterprise Network Segmentation

# Enterprise Network Segmentation & Inter-VLAN Routing

## Overview
This project demonstrates the design and implementation of an enterprise-style network using VLAN segmentation and inter-VLAN routing. The topology simulates a small office environment with multiple departments, each isolated at Layer 2 and routed securely at Layer 3 using a router-on-a-stick configuration.

The lab emphasizes real-world networking fundamentals including VLAN design, 802.1Q trunking, and gateway configuration.

---

## Network Architecture

**Departments & VLANs**
- Finance — VLAN 10 — 192.168.10.0/24
- Operations — VLAN 20 — 192.168.20.0/24
- Admin — VLAN 30 — 192.168.30.0/24

**Core Components**
- Cisco 2960 Access Switch
- Cisco 2911 Router (Router-on-a-Stick)
- Wired PCs per department
- Admin server and network printer
- Wireless access point with laptop client

---

## Key Features
- VLAN-based network segmentation
- 802.1Q trunking between switch and router
- Router subinterfaces providing default gateways
- Static IP addressing for infrastructure devices
- Wired and wireless client connectivity
- Verified inter-VLAN communication via ICMP testing

---

## Router Configuration (Summary)
- Subinterfaces on GigabitEthernet0/0
- Each subinterface mapped to a VLAN
- Default gateway IP assigned per VLAN

Example:
- Gi0/0.10 → VLAN 10 → 192.168.10.1
- Gi0/0.20 → VLAN 20 → 192.168.20.1
- Gi0/0.30 → VLAN 30 → 192.168.30.1

---

## Switch Configuration (Summary)
- Access ports assigned per department VLAN
- Trunk port configured toward router
- VLANs created and verified

---

## Validation & Testing
- Same-VLAN device communication verified
- Inter-VLAN routing validated via successful cross-VLAN pings
- Gateway reachability confirmed for all subnets

---

## Files Included
- `inter-vlan-routing.pkt` — Packet Tracer project file
- `network-topology-ivr', 'routing-config', and 'switch-config' — Labeled network diagrams
- `README.md` — Project documentation

---

## Skills Demonstrated
- VLAN design and segmentation
- Layer 2 vs Layer 3 networking concepts
- Cisco IOS configuration
- Network troubleshooting and validation
- Enterprise network documentation
