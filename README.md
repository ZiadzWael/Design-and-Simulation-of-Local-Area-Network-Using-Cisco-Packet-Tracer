📋 Project Overview
This project implements a simulated multi-department Local Area Network (LAN) for a university faculty using Cisco Packet Tracer. The network employs VLAN technology to logically separate different academic departments while maintaining controlled inter-department communication through inter-VLAN routing. Based on concepts from the research paper "Design and Simulation of Local Area Network Using Cisco Packet Tracer", this implementation provides a functional model for network segmentation in educational institutions.

👥 Project Team
Development Team:

Ziad Wael (221001480) - Network architecture, VLAN configuration, router setup

Sama Eldessouky (221000579) - Documentation, testing, IP addressing scheme

Abdullah Ramzy (221001781) - Physical topology, switch configuration, validation

Supervisor: Dr. Islam Tharwat Abdelhalim

🔧 Technical Implementation
Network Architecture
Router: 1 × Cisco 2911 (R1) with router-on-a-stick configuration

Switches: 2 × Cisco 2960-24TT (SW1, SW2)

End Devices: 8 × PCs (2 per department), 1 × DNS Server

Cabling: Copper Straight-Through for all connections

VLAN Segmentation
VLAN ID	VLAN Name	Department	IP Subnet
10	CS_Dept	Computer Science	192.168.10.0/24
20	ENG_Dept	Engineering	192.168.20.0/24
30	BUS_Dept	Business	192.168.30.0/24
40	BIO_Dept	Biotechnology	192.168.40.0/24
99	SERVERS	Server Network	192.168.99.0/24

Core Features Implemented
✅ VLAN-based departmental network segmentation

✅ Inter-VLAN routing using router-on-a-stick methodology

✅ Hierarchical network design (access-distribution-routing)

✅ DNS service deployment for name resolution

✅ Comprehensive connectivity testing and validation

✅ Static IP addressing scheme across all devices

📂 Repository Structure
text
├── packet-tracer-files/
│   ├── final-network-design.pkt    # Complete network simulation
│   └── network-topology.png        # Visual representation
├── configurations/
│   ├── switch-config.txt           # VLAN and port configurations
│   ├── router-config.txt           # Inter-VLAN routing setup
│   └── ip-addressing.txt          # Complete IP scheme
├── documentation/
│   ├── project-report.pdf          # Comprehensive documentation
│   └── implementation-guide.md     # Step-by-step setup
├── screenshots/
│   ├── vlan-verification.png      # show vlan brief outputs
│   ├── connectivity-tests.png     # Ping test results
│   └── router-interfaces.png      # Router configuration
└── README.md                      # This file
🚀 Getting Started
Prerequisites
Cisco Packet Tracer (Version 8.x or later)

Basic understanding of networking concepts (VLANs, routing, IP addressing)

Quick Start
Clone this repository: git clone https://github.com/ZiadzWael/Design-and-Simulation-of-Local-Area-Network-Using-Cisco-Packet-Tracer.git

Open packet-tracer-files/LAN Newtork Simulation.pkt in Cisco Packet Tracer

Explore the network topology and device configurations

Run connectivity tests between different VLANs

Review configuration files for implementation details

Testing the Network
From any PC in the simulation:

Test intra-VLAN connectivity: ping another PC in the same department

Test inter-VLAN routing: ping a PC in a different department

Test DNS resolution: ping hostnames (e.g., cs1.lan, dns1.lan)

Access the project web page: http://192.168.99.10

📊 Verification Commands
Key commands used to verify network functionality:

bash
# On switches
show vlan brief          # Verify VLAN port assignments
show interfaces trunk    # Check trunk port status

# On router
show ip interface brief  # Verify subinterface configurations
show running-config      # View complete router configuration

# On PCs
ping <IP_address>        # Test connectivity
tracert <IP_address>     # Trace packet path
🎯 Project Outcomes
Successfully Demonstrated
Proper VLAN segmentation and port assignment

Functional inter-VLAN routing between departments

Correct IP addressing and gateway configuration

Working DNS resolution across all VLANs

Hierarchical network design principles

Educational Value
This project provides practical implementation of theoretical networking concepts, including VLAN technology, subnetting, router configuration, and network service deployment. It serves as a comprehensive example of enterprise network design principles applied to an educational environment.
