# LAN Network Simulation Project

## Project Overview
This project implements a multi-department Local Area Network (LAN) simulation using Cisco Packet Tracer. The design demonstrates VLAN segmentation and inter-VLAN routing for a university faculty environment with four academic departments.

## Project Versions
- **v1**: Basic VLAN implementation with static IP addressing, inter-VLAN routing, and core network services
- **v2**: Enhanced implementation with all v1 features plus DHCP server, wireless access, mail server, and enhanced DNS configuration

## Technical Specifications

### VLAN Architecture
| VLAN ID | VLAN Name | Department | IP Subnet | v2 Enhancements |
|---------|-----------|------------|-----------|-----------------|
| 10 | CS_Dept | Computer Science | 192.168.10.0/24 | Added wireless devices (Laptop-CS, AP-CS) |
| 20 | ENG_Dept | Engineering | 192.168.20.0/24 | Added wireless devices (Laptop-ENG, AP-ENG) |
| 30 | BUS_Dept | Business | 192.168.30.0/24 | - |
| 40 | BIO_Dept | Biotechnology | 192.168.40.0/24 | - |
| 99 | SERVERS | Server Network | 192.168.99.0/24 | Added MAIL1 server |

### Device Addressing
| Device | VLAN | IP Address | Gateway | DNS Server | v2 Notes |
|--------|------|------------|---------|------------|----------|
| CS1 | 10 | 192.168.10.10 | 192.168.10.1 | 192.168.99.10 | Static |
| CS2 | 10 | DHCP: 192.168.10.50+ | 192.168.10.1 | 192.168.99.10 | v2 DHCP |
| ENG1 | 20 | 192.168.20.10 | 192.168.20.1 | 192.168.99.10 | Static |
| ENG2 | 20 | DHCP: 192.168.20.50+ | 192.168.20.1 | 192.168.99.10 | v2 DHCP |
| BUS1 | 30 | 192.168.30.10 | 192.168.30.1 | 192.168.99.10 | Static |
| BUS2 | 30 | DHCP: 192.168.30.50+ | 192.168.30.1 | 192.168.99.10 | v2 DHCP |
| BIO1 | 40 | 192.168.40.10 | 192.168.40.1 | 192.168.99.10 | Static |
| BIO2 | 40 | DHCP: 192.168.40.50+ | 192.168.40.1 | 192.168.99.10 | v2 DHCP |
| Laptop-CS | 10 | DHCP: 192.168.10.50+ | 192.168.10.1 | 192.168.99.10 | v2 Wireless |
| Laptop-ENG | 20 | DHCP: 192.168.20.50+ | 192.168.20.1 | 192.168.99.10 | v2 Wireless |
| DNS1 | 99 | 192.168.99.10 | 192.168.99.1 | 192.168.99.10 | v2: Also DHCP Server |
| MAIL1 | 99 | 192.168.99.20 | 192.168.99.1 | 192.168.99.10 | v2 New Server |

### v2 New Features

#### DHCP Configuration
| VLAN | DHCP Pool | IP Range | Gateway | Max Users |
|------|-----------|----------|---------|-----------|
| 10 (CS Dept) | VLAN10_CS | 192.168.10.50-74 | 192.168.10.1 | 25 |
| 20 (ENG Dept) | VLAN20_ENG | 192.168.20.50-74 | 192.168.20.1 | 25 |
| 30 (BUS Dept) | VLAN30_BUS | 192.168.30.50-74 | 192.168.30.1 | 25 |
| 40 (BIO Dept) | VLAN40_BIO | 192.168.40.50-74 | 192.168.40.1 | 25 |

#### Wireless Network Configuration
| Access Point | SSID | Security | Password | VLAN |
|-------------|------|----------|----------|------|
| AP-CS | CS_Dept_WiFi | WPA2-PSK | CSdept2026 | 10 |
| AP-ENG | ENG_Dept_WiFi | WPA2-PSK | ENGdept2026 | 20 |

#### Mail Server Configuration (v2)
- **Server**: MAIL1 (192.168.99.20)
- **Domain**: university.lan
- **Protocols**: SMTP (port 25), POP3 (port 110)
- **Email Address**: mail.university.lan

## Implementation Features

### v1 Core Features:
- VLAN segmentation of four academic departments
- Inter-VLAN routing using router-on-a-stick configuration
- DNS server with hostname resolution
- Web server accessible from all departments
- Hierarchical network design

### v2 Enhanced Features:
- **DHCP Services**: Automatic IP address assignment across all VLANs
- **Wireless Networking**: Secure WPA2 wireless access for CS and Engineering departments
- **Email Services**: Complete mail server with user accounts and cross-VLAN accessibility
- **Enhanced DNS**: Additional records for new services and devices
- **Mixed Addressing**: Combination of static and dynamic IP allocation
- **DHCP Relay**: Router configured as DHCP relay agent for all VLANs

## Testing Results
- Successful intra-VLAN communication within departments
- Functional inter-VLAN routing between departments
- Server accessibility from all network segments
- Name resolution through DNS services
- **v2 Additional Tests**:
  - DHCP address assignment across all VLANs
  - Wireless connectivity with WPA2 security
  - Email send/receive between departments
  - Cross-VLAN service access from wireless clients

## Conclusion
This project successfully implemented a comprehensive multi-department LAN using Cisco Packet Tracer, demonstrating practical application of VLAN technology and inter-VLAN routing. Version 2 extends the basic implementation with enterprise-grade network services including DHCP automation, wireless access, and email services, providing a complete model for modern departmental network design in educational institutions.
