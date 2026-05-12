**Enterprise Building Multi-Floor Network Topology Lab**

**Overview**

This project demonstrates a multi-site enterprise network topology built in Cisco Packet Tracer using:

* Router-on-a-Stick Inter-VLAN Routing
* OSPF Dynamic Routing
* VLAN Segmentation
* DHCP Configuration
* SSH Remote Access
* Wireless LAN Support
* Port Security
* Multi-router WAN Connectivity

The lab simulates a three-floor enterprise building network connected through WAN serial links and segmented VLAN architecture.

**Floor Mapping**

| Abbreviation | Meaning      |
| ------------ | ------------ |
| FF           | First Floor  |
| SF           | Second Floor |
| TF           | Third Floor  |

---

**Network Devices**

**Routers**

* FFROUTER (First Floor Router)
* SFROUTER (Second Floor Router)
* TFROUTER (Third Floor Router)

**Switches**

* FFSW (First Floor Switch)
* SFSW (Second Floor Switch)
* TFSW (Third Floor Switch)

---

**Technologies Used**

* Cisco IOS 15.1
* OSPF Area 0
* IEEE 802.1Q Trunking
* Router-on-a-Stick
* DHCP Services
* SSH Access
* Port Security
* VLAN Segmentation
* Wireless LAN Integration

---

**Network Topology**

**Third Floor (TF) Networks**

| VLAN     | Purpose            | Network          |
| -------- | ------------------ | ---------------- |
| VLAN 10  | Department Network | 192.168.1.0/24   |
| VLAN 20  | Department Network | 192.168.2.0/24   |
| VLAN 110 | Wireless LAN       | 192.168.110.0/24 |

**Second Floor (SF) Networks**

| VLAN     | Purpose            | Network          |
| -------- | ------------------ | ---------------- |
| VLAN 30  | Department Network | 192.168.3.0/24   |
| VLAN 40  | Department Network | 192.168.4.0/24   |
| VLAN 50  | Department Network | 192.168.5.0/24   |
| VLAN 100 | Wireless LAN       | 192.168.100.0/24 |

**First Floor (FF) Networks**

| VLAN    | Purpose            | Network        |
| ------- | ------------------ | -------------- |
| VLAN 60 | Department Network | 192.168.6.0/24 |
| VLAN 70 | Department Network | 192.168.7.0/24 |
| VLAN 80 | Department Network | 192.168.8.0/24 |
| VLAN 90 | Wireless LAN       | 192.168.9.0/24 |

---

**Inter-Floor WAN Connectivity**

| Connection          | Network       |
| ------------------- | ------------- |
| TFROUTER ↔ FFROUTER | 10.10.10.4/30 |
| TFROUTER ↔ SFROUTER | 10.10.10.8/30 |
| SFROUTER ↔ FFROUTER | 10.10.10.0/30 |

---

**Routing Configuration**

**OSPF**

All routers participate in:

* OSPF Process ID: 1
* Area: 0

**Features**

* Dynamic route advertisement
* Automatic route learning
* Full inter-site communication
* Scalable enterprise routing design

---

**Router-on-a-Stick Configuration**

Each router uses subinterfaces on GigabitEthernet0/0:

Example:


interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.1.1 255.255.255.0


**Benefits**

* Inter-VLAN communication
* VLAN traffic segmentation
* Efficient use of physical interfaces

---

**DHCP Configuration**

Each router acts as a DHCP server for local VLANs.

**Example DHCP Pool**


ip dhcp pool vlan10
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1


**Features**

* Automatic IP assignment
* Centralized network management
* Reduced manual configuration

---

**SSH Remote Management**

SSH is configured on all routers.

**Configuration Features**

* Local username authentication
* VTY line security
* SSH-only remote access

Example:


line vty 0 4
 login local
 transport input ssh


---

**Port Security**

Port security is configured on TFSW.

**Secure Ports**

| Interface | Maximum MAC Addresses | Violation Action |
| --------- | --------------------- | ---------------- |
| Fa0/2     | 1                     | Shutdown         |
| Fa0/4     | 1                     | Shutdown         |

**Verification**


show port-security


**Security Benefits**

* Prevents unauthorized device connections
* Protects against MAC flooding attacks
* Improves LAN security

---

**Wireless Networks by Floor**

| Router   | Wireless VLAN | Network          |
| -------- | ------------- | ---------------- |
| TFROUTER | VLAN 110      | 192.168.110.0/24 |
| SFROUTER | VLAN 100      | 192.168.100.0/24 |
| FFROUTER | VLAN 90       | 192.168.9.0/24   |

---

**Security Features**

**Implemented Security**

* Enable secret passwords
* SSH remote access
* Local user authentication
* Port security
* VLAN segmentation

---

**Verification Commands**

**Routing Verification**


show ip route

show ip ospf neighbor


**VLAN Verification**


show vlan brief

show interfaces trunk


**DHCP Verification**


show ip dhcp binding

show ip dhcp pool


**Port Security Verification**


show port-security


**Connectivity Testing**


ping

traceroute


---

**Enterprise Networking Skills Demonstrated**

* Enterprise Network Design
* VLAN Configuration
* Dynamic Routing (OSPF)
* Router-on-a-Stick
* DHCP Deployment
* SSH Hardening
* Port Security
* WAN Configuration
* Cisco IOS Administration
* Network Troubleshooting

---




**Future Improvements**

Possible enhancements:

* ACL implementation
* NAT/PAT configuration
* Syslog server integration
* NTP configuration
* AAA authentication
* EtherChannel
* STP optimization
* Redundant links
* IPv6 support

---

**Project Highlights**

* Multi-floor enterprise network simulation
* VLAN-based traffic segmentation
* Dynamic routing using OSPF
* Inter-VLAN communication
* DHCP deployment across multiple floors
* Wireless LAN integration
* Port security implementation
* SSH remote administration
* WAN serial connectivity
* Cisco enterprise network design

---

**Author**

Ravi Kumar

---

**License**

This project is for educational and portfolio purposes.
