# Comprehensive Network Infrastructure - CCNA Project

## 📝 Project Description
*This project was developed as a hands-on demonstration of my networking expertise and CCNA-level proficiency. It showcases a complex enterprise environment that integrates core routing, redundant switching, and WLAN. My goal was to move beyond basic connectivity and implement real-world scenarios.*

## 🌐 Topology Overview
The infrastructure is divided into three distinct zones:
1.  **Corporate Headquarters (HQ):**
    * Core Routers: **R1, R2, R3** running **OSPFv2** for dynamic routing.
    * Access Layer: Three distinct LANs with VLSM segmentation (LAN1, LAN2, LAN3).
2.  **Remote Branch:**
    * Router-on-a-Stick configuration for VLAN management.
    * Redundant switching with **LACP EtherChannel**.
3.  **Service Provider (ISP):**
    * Simulated internet cloud providing public IP reachability.
    * **GRE Tunnel (Site-to-Site)** established between HQ (R1) and Branch.

## 📊 Addressing Table
| Device       | Interface | IP Address     | Subnet/Mask       | Description      |
| :----------- | :-------- | :------------- | :---------------- | :--------------- |
| **R1**       | G0/0/0    | 192.168.10.1   | 192.168.10.0/25   | HQ LAN 1 Gateway |
| **R2**       | G0/0/0    | 192.168.10.129 | 192.168.10.128/26 | HQ LAN 2 Gateway |
| **R3**       | G0/0/1    | 192.168.10.193 | 192.168.10.192/27 | HQ LAN 3 Gateway |
| **R-Branch** | G0/0/1.10 | 172.16.10.1    | 172.16.10.0/24    | Branch VLAN 10   |
| **R-Branch** | G0/0/1.30 | 172.16.30.1    | 172.16.30.0/24    | Branch VLAN 30   |
| **Tunnel 0** | Tunnel0   | 10.0.0.x       | 10.0.0.0/30       | GRE Tunnel Link  |

## 🛠️ Implemented Features & Technologies

### 1. Routing & Connectivity
* **OSPFv2 (Single Area):** Dynamic routing within HQ to ensure full reachability and redundancy.
* **GRE Tunnel:** Encapsulated Site-to-Site connectivity allowing private traffic over a public ISP.
* **NAT/PAT:** Network Address Translation implemented on edge routers for Internet access.
* **Static Routes:** Floating static routes used for tunnel redirection.


### 2. Switching & Layer 2
* **EtherChannel (LACP):** Link aggregation between Branch switches for increased bandwidth and failover.
* **VLANs & Trunking:** Logical separation of Data, Voice, and Guest traffic using 802.1Q.
* **Spanning Tree:** Loop prevention.


### 3. Security
* **Extended ACLs:** Granular traffic filtering (e.g., blocking LAN1 access to specific web resources like 8.8.8.8).
* **Port Security:** Restricted access on switch ports to authorized MAC addresses only.
* **SSH v2:** Encrypted remote management across all infrastructure devices.
* **Banners:** Professional MOTD and Login banners for legal compliance.


### 4. IP Services
* **DHCP Server:** Automatic IP allocation for all end-devices with appropriate excluded ranges.
* **Wireless:** Secured WiFi access for branch mobile users.

## 🚀 Verification
To verify the functionality of this lab:
1.  **Ping Test:** Run a ping from `PC0` (HQ) to `Smartphone0` (Branch) to verify GRE Tunnel routing.
2.  **ACL Test:** Open the Web Browser on `PC0` and try to access `8.8.8.8`. It should be denied by the Extended ACL.
3.  **Redundancy Test:** Shutdown one link in the EtherChannel bundle; traffic should continue to flow without interruption.


*For a list of planned features and known issues, please refer to the [[TODO.md]] file.*
---
