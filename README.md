# GNS3 Layer 2 VLAN Trunking Lab

A verified networking lab demonstrating the deployment of Virtual Local Area Networks (VLANs), 802.1Q Trunking Encapsulation, and traffic isolation across a multi-switch local area network backbone. Simulated effectively on GNS3 using IOU (IOS on Unix) switches.

## Topology Diagram

![GNS3 Network Topology Diagram](GNS3-Layer2-Trunking-Lab/topology.png)

---

## Project Overview
This repository contains a complete Cisco Layer 2 Switch configuration lab implemented in **GNS3**. The project focuses on optimizing broadcast domains, enhancing local network security through strict VLAN segmentation, and ensuring loop-free redundancy using Spanning Tree Protocol.

### Key Technical Concepts Implemented:
* **802.1Q Trunking:** Configured on inter-switch links to allow seamless traffic transport for multiple VLANs across the core switch backbone.
* **VLAN Database Integrity:** Proper implementation of local VLAN databases on each switch ensuring ports map seamlessly without operational downtime.
* **Rapid Spanning Tree Protocol (Rapid-PVST):** Enabled globally to prevent Layer 2 loops and ensure faster convergence across the switching infrastructure.
* **Traffic Isolation & Security:** Verified strict segmentation where hosts within the same VLAN communicate successfully (End-to-End reachability), while cross-VLAN traffic is completely blocked without a Layer 3 routing engine.

---

## Network Architecture Details

| VLAN ID | VLAN Name | Network Purpose | Target Subnet (Logical) |
| :--- | :--- | :--- | :--- |
| **VLAN 10** | Management | Switch management and local admin access | 10.10.10.0/24 |
| **VLAN 20** | Data_A | Department A user endpoint traffic | 10.10.20.0/24 |
| **VLAN 30** | Data_B | Department B user endpoint traffic | 10.10.30.0/24 |

---

## Repository Structure
* `/GNS3-Layer2-Trunking-Lab/Configurations`: Contains the clean, deployment-ready running configurations (`.txt`) for all three switches (`IOU1`, `IOU2`, `IOU3`).
* `/GNS3-Layer2-Trunking-Lab/pings`: Includes the verified host-to-host ICMP ping validation screenshot (`ping-results-and-vlan-isolation.png.png`).
* `GNS3-Layer2-Trunking-Lab/topology.png`: The network architecture and device interconnection blueprint from GNS3 (displayed above).
* `GNS3-Layer2-Trunking-Lab/show-interfaces-trunk-results.png.png`: Verified CLI output screenshot displaying operational trunk links and allowed VLANs.

---

## How to Deploy
1. Clone this repository to your local directory.
2. Import the switch configuration files found in the `/GNS3-Layer2-Trunking-Lab/Configurations` folder directly into your GNS3 IOU switch nodes or live Cisco hardware.
