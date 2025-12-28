# LAN Network Simulation Project

## Project Overview
This project (v1) implements a multi-department Local Area Network (LAN) simulation using Cisco Packet Tracer. The design demonstrates VLAN segmentation and inter-VLAN routing for a university faculty environment with four academic departments.

## Project Structure
Main (v1)/
├── implementation-guide.pdf
├── LAN-Network-Simulation.pkt
└── network-project.pdf
## Technical Specifications

### VLAN Architecture
| VLAN ID | VLAN Name   | Department       | IP Subnet        |
|---------|-------------|------------------|------------------|
| 10      | CS_Dept     | Computer Science | 192.168.10.0/24  |
| 20      | ENG_Dept    | Engineering      | 192.168.20.0/24  |
| 30      | BUS_Dept    | Business         | 192.168.30.0/24  |
| 40      | BIO_Dept    | Biotechnology    | 192.168.40.0/24  |
| 99      | SERVERS     | Server Network   | 192.168.99.0/24  |

### Device Addressing
| Device | VLAN | IP Address      | Gateway         | DNS Server     |
|--------|------|-----------------|-----------------|----------------|
| CS1    | 10   | 192.168.10.10   | 192.168.10.1    | 192.168.99.10  |
| CS2    | 10   | 192.168.10.20   | 192.168.10.1    | 192.168.99.10  |
| ENG1   | 20   | 192.168.20.10   | 192.168.20.1    | 192.168.99.10  |
| ENG2   | 20   | 192.168.20.20   | 192.168.20.1    | 192.168.99.10  |
| BUS1   | 30   | 192.168.30.10   | 192.168.30.1    | 192.168.99.10  |
| BUS2   | 30   | 192.168.30.20   | 192.168.30.1    | 192.168.99.10  |
| BIO1   | 40   | 192.168.40.10   | 192.168.40.1    | 192.168.99.10  |
| BIO2   | 40   | 192.168.40.20   | 192.168.40.1    | 192.168.99.10  |
| DNS1   | 99   | 192.168.99.10   | 192.168.99.1    | 192.168.99.10  |

## Implementation Features
- VLAN segmentation of four academic departments
- Inter-VLAN routing using router-on-a-stick configuration
- DNS server with hostname resolution
- Web server accessible from all departments
- Hierarchical network design

## Testing Results
- Successful intra-VLAN communication within departments
- Functional inter-VLAN routing between departments
- Server accessibility from all network segments
- Name resolution through DNS services
