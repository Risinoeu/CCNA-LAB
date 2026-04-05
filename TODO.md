# 🛠 Project Status & Future Improvements

### ⚠️ Current Project Status

This project is a functional CCNA-level simulation, but it is currently a **Work in Progress**. While the core routing (OSPF, GRE) and switching (VLANs, EtherChannel) are fully operational.

Please note that some minor configuration details may not be fully completed yet. Certain advanced security and management features are slated for future updates as outlined below.

---

### 🚀 Planned Enhancements

#### 1. Security & Hardening

- **SSH Implementation:** Transition from Telnet to SSH v2 across all HQ routers (R1, R2, R3) and Switches (SW1, SW2, SW3) to ensure encrypted management.

- **DHCP Snooping & DAI:** Implement Layer 2 security features on access switches to prevent rogue DHCP servers and ARP spoofing.
   

#### 2. Scalability & Routing
  
- **IPv6 Dual-Stack:** Implement IPv6 addressing alongside IPv4, including OSPFv3 and IPv6 static routing.

- **HSRP/VRRP:** Introduce First Hop Redundancy Protocols (FHRP) to ensure seamless gateway failover for end-users.


#### 3. Management & Monitoring

- **NTP Synchronization:** Configure a central NTP server to synchronize clocks across all network devices for accurate logging.

- **Syslog Server:** Set up remote logging to a Syslog server to track network events and potential security breaches in real-time.