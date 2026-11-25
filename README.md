# Enterprise HQ–Branch Network Design and Implementation

## Project Overview

This project demonstrates the design and implementation of an enterprise network connecting a Head Office (HQ) and a Branch Office using Cisco Packet Tracer.
The network provides communication between different departments, secure access control, dynamic routing, IP address management, and simulated Internet connectivity.
The project focuses on practical networking skills used in Network Support, NOC, and Junior Network Engineer roles.

## Project Objectives

- Design an enterprise network with HQ and Branch offices.
- Implement VLANs for departmental network segmentation.
- Configure inter-VLAN routing using Router-on-a-Stick.
- Configure DHCP for automatic IP address assignment.
- Implement OSPF dynamic routing between HQ and Branch.
- Apply ACLs to control network traffic.
- Configure switch port security.
- Configure SSH for secure remote management.
- Implement NAT/PAT for simulated Internet access.
- Perform connectivity testing and troubleshooting.

## Network Topology

**Network Diagram:**

Add your Cisco Packet Tracer topology screenshot here.

![Enterprise Network Topology](
enterprise-network-hq-branch/screenshots/network-topology.png)

## Technologies and Tools Used

| Technology | Purpose |
|---|---|
| Cisco Packet Tracer | Network simulation |
| VLAN | Network segmentation |
| 802.1Q Trunking | VLAN communication |
| Router-on-a-Stick | Inter-VLAN routing |
| DHCP | Automatic IP assignment |
| OSPF | Dynamic routing |
| ACL | Traffic filtering and security |
| Port Security | Switch port protection |
| SSH | Secure remote management |
| NAT/PAT | Private-to-public IP translation |
| IPv4 | Network addressing |

## Network Architecture

The network consists of:

- **Head Office (HQ):** HR, IT, Finance, and Server departments.
- **Branch Office:** Branch user network.
- **ISP Router:** Simulates an Internet Service Provider.
- **Internet Server:** Simulates an external Internet destination.

## IP Addressing Table

| Network / Department | VLAN | Network Address | Default Gateway |
|---|---:|---|---|
| HQ - HR | 10 | 192.168.10.0/24 | 192.168.10.1 |
| HQ - IT | 20 | 192.168.20.0/24 | 192.168.20.1 |
| HQ - Finance | 30 | 192.168.30.0/24 | 192.168.30.1 |
| HQ - Server | 40 | 192.168.40.0/24 | 192.168.40.1 |
| Branch Users | 50 | 192.168.50.0/24 | 192.168.50.1 |
| HQ–Branch WAN | — | 10.0.0.0/30 | R1: 10.0.0.1 / R2: 10.0.0.2 |
| R1–ISP WAN | — | 203.0.113.0/30 | R1: 203.0.113.1 / ISP: 203.0.113.2 |
| Internet Server Network | — | 198.51.100.0/24 | 198.51.100.1 |

## Implementation Details

### 1. VLAN Configuration

Created separate VLANs for different departments:

- VLAN 10 – HR
- VLAN 20 – IT
- VLAN 30 – Finance
- VLAN 40 – Server
- VLAN 50 – Branch Users

Configured access ports and trunk ports for VLAN communication.

### 2. DHCP Configuration

Configured DHCP pools on the routers to automatically assign IP addresses to devices in their respective networks.

### 3. Inter-VLAN Routing

Implemented Router-on-a-Stick using 802.1Q encapsulation to enable communication between different HQ VLANs.

### 4. OSPF Dynamic Routing

Configured OSPF Process ID 1 in Area 0 between HQ and Branch routers.

Verified OSPF neighbor relationships and learned routes.

### 5. Access Control Lists (ACL)

Implemented extended ACLs to control communication between departments.

- Restricted HR-to-Finance communication.
- Configured Branch traffic restrictions.
- Applied HTTP-specific access rules for the internal server.

### 6. Switch Port Security

Configured port security on the HQ switch to restrict unauthorized devices from connecting to a protected switch port.

Configured:

- Maximum MAC addresses.
- Static and sticky MAC address learning.
- Shutdown violation mode.

### 7. SSH Remote Management

Configured SSH version 2 on the HQ router using RSA encryption and local authentication.

### 8. NAT/PAT Configuration

Configured NAT Overload (PAT) on the HQ router.

- Identified inside and outside interfaces.
- Created an access list for internal networks.
- Used the ISP-facing interface as the public IP.
- Configured default routing toward the ISP.

### 9. Simulated Internet Connectivity

Added an ISP router and an external Server-PT device to simulate Internet access.

Successfully tested connectivity from HQ and Branch PCs to the external server.

## Testing and Verification

| Test | Result |
|---|---|
| DHCP IP assignment | Successful |
| Inter-VLAN connectivity | Successful |
| OSPF neighbor formation | Verified |
| HQ-to-Branch routing | Successful |
| ACL traffic restriction | Tested |
| Port security | Tested |
| HQ-to-Internet Server ping | Successful |
| Branch-to-Internet Server ping | Successful |
| SSH remote login | Pending verification |

## Troubleshooting Commands

The following Cisco IOS commands were used during configuration and verification:

```cisco
show ip interface brief
show vlan brief
show interfaces trunk
show ip route
show ip ospf neighbor
show ip route ospf
show access-lists
show port-security interface fa0/1
show ip ssh
show ip nat translations
show ip nat statistics
ping
traceroute
```

## Skills Demonstrated

- Network design and implementation
- VLAN and trunk configuration
- IP addressing and subnetting
- DHCP configuration
- Inter-VLAN routing
- OSPF dynamic routing
- ACL configuration and troubleshooting
- Switch port security
- SSH configuration
- NAT/PAT implementation
- Network connectivity troubleshooting

## Conclusion

This project provided practical experience in designing, configuring, and troubleshooting a simulated enterprise network environment.

It demonstrates fundamental networking concepts and practical Cisco IOS configuration skills relevant to Network Support Engineer, NOC Engineer, and Junior Network Engineer positions.

---


**Author:** Ankur Rahate
