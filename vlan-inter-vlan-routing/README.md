# Inter-VLAN Routing – Router-on-a-Stick (Cisco Packet Tracer)

## Overview
This project demonstrates a small office network implementing **inter-VLAN routing** using a **router-on-a-stick** design. Multiple VLANs are configured on a Layer 2 switch, with routing handled by a single router interface using 802.1Q subinterfaces.

The lab simulates segmented departments with isolated broadcast domains while maintaining controlled Layer 3 connectivity.

---

## Network Topology
- **Router:** Cisco 2911 (Router-on-a-Stick)
- **Switch:** Cisco 2960 (Layer 2)
- **End Devices:** 3 PCs representing separate departments
- **Trunk Link:** Switch ↔ Router (802.1Q)

Refer to `topology.png` for a labeled diagram.

---

## VLAN Design

| VLAN | Name        | Subnet              | Gateway          |
|-----:|-------------|---------------------|------------------|
| 10   | Finance     | 192.168.10.0/24     | 192.168.10.1     |
| 20   | Operations  | 192.168.20.0/24     | 192.168.20.1     |
| 30   | Admin       | 192.168.30.0/24     | 192.168.30.1     |

---

## Key Configurations

### Switch (Access Layer)
- Created VLANs 10, 20, and 30
- Assigned access ports:
  - Fa0/1 → VLAN 10 (Finance)
  - Fa0/2 → VLAN 20 (Operations)
  - Fa0/3 → VLAN 30 (Admin)
- Configured **Gig0/1** as an 802.1Q trunk to the router
- Allowed VLANs 10, 20, 30 on the trunk

### Router (Inter-VLAN Routing)
- Configured subinterfaces on **GigabitEthernet0/0**
- Enabled 802.1Q encapsulation per VLAN
- Assigned gateway IP addresses for each subnet

Example:
- Gi0/0.10 → VLAN 10 → 192.168.10.1/24
- Gi0/0.20 → VLAN 20 → 192.168.20.1/24
- Gi0/0.30 → VLAN 30 → 192.168.30.1/24

---

## Verification & Testing
- Verified trunk operation using `show interfaces trunk`
- Verified VLAN assignments using `show vlan brief`
- Confirmed router subinterfaces with `show ip interface brief`
- Tested inter-VLAN connectivity using ICMP (ping)
- Observed ARP and ICMP behavior in Packet Tracer Simulation Mode

---

## Files Included
- `vlan-router-project.pkt` – Cisco Packet Tracer project file
- `topology.png` – Labeled network topology diagram

---

## Skills Demonstrated
- VLAN configuration and segmentation
- 802.1Q trunking
- Inter-VLAN routing (router-on-a-stick)
- Layer 2 vs Layer 3 troubleshooting
- IP addressing and subnetting
- Network verification and diagnostics

---

## Notes
This project is designed to be viewed both visually (via screenshot) and interactively (by opening the Packet Tracer file). All configurations follow standard enterprise networking practices.
