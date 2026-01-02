# Small Office Network with Router-Based DHCP

## Overview
This project demonstrates the design, configuration, and validation of a small office local area network (LAN) using Cisco Packet Tracer. The goal was to create a reliable network that automatically assigns IP configuration to endpoints and allows full internal connectivity through proper switching and routing.

## Network Topology
The network consists of:
- One Cisco router acting as the default gateway and DHCP server
- One Layer-2 switch providing internal connectivity
- Three end-user PCs receiving dynamic IP addresses

## Design Decisions
- A router-based DHCP model was chosen to centralize IP address management
- A Layer-2 switch was used to efficiently connect multiple endpoints within the same subnet
- Endpoints were configured to receive network settings dynamically to reduce manual configuration and errors

## Key Configurations
- Router interface configuration for LAN connectivity
- DHCP pool configuration with defined subnet, gateway, and excluded addresses
- Switch access ports configured for end-user devices
- PortFast enabled on access ports to reduce Spanning Tree convergence delay

## Validation and Testing
- Verified DHCP lease assignment on each endpoint using `ipconfig`
- Confirmed Layer 3 connectivity by pinging the default gateway
- Tested end-to-end host communication using ICMP between multiple endpoints

## Tools and Technologies
- Cisco Packet Tracer
- TCP/IP
- DHCP
- ICMP
- Layer 2 switching and basic routing concepts

## Outcome
The network successfully provides automated IP configuration and reliable internal communication, simulating a real-world small office environment and reinforcing foundational networking concepts.
