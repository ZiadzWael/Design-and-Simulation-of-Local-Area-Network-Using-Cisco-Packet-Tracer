# Design and Simulation of a University LAN using Cisco Packet Tracer

## 📖 Project Overview
This project demonstrates the practical design, configuration, and simulation of a functional Local Area Network (LAN) for a hypothetical university's College of Engineering. Implemented in **Cisco Packet Tracer**, the network model incorporates core networking concepts such as **VLAN segmentation, subnetting, and inter-VLAN routing** to create a secure and efficient departmental network.

## ✨ Key Features
*   **Hierarchical Network Design**: A structured topology using core, distribution, and access layer switches.
*   **Departmental Segmentation**: Implementation of Virtual LANs (VLANs) to logically separate traffic for different engineering departments (e.g., Civil, Electrical, Computer Science).
*   **Inter-VLAN Routing**: Configuration of a Layer 3 switch to enable communication between different VLANs.
*   **Simulated Network Services**: Deployment of DHCP and DNS servers for automatic IP address assignment and hostname resolution.
*   **Connectivity Validation**: Comprehensive testing using `ping`, `tracert`, and CLI commands to verify the design.

## 🛠️ Technologies Used
*   **Cisco Packet Tracer** (Version 8.x or later recommended)
*   Networking Protocols: VLAN (802.1Q), DHCP, DNS, Static & Dynamic Routing

## 🚀 Getting Started

### Prerequisites
1.  Download and install the latest version of [**Cisco Packet Tracer**](https://www.netacad.com/courses/packet-tracer).
2.  Clone this repository to your local machine:
    ```bash
    git clone https://github.com/[your-username]/LAN-Simulation-Cisco-Packet-Tracer.git
    ```

### How to Run the Simulation
1.  Open **Cisco Packet Tracer**.
2.  Navigate to `File > Open` and select the `project-files/final-network-design.pkt` file from this repository.
3.  Enter **Simulation Mode** (clock icon in the bottom right).
4.  Use the **Add Simple PDU** tool (the envelope icon) to click from a PC in one VLAN to a server in another to generate and visualize network traffic.

## 📂 Project Files
*   `final-network-design.pkt`: The main Packet Tracer file containing the complete network.
*   `Network-Design-Specification.md`: Detailed explanation of the topology and design choices.
*   `IP-Addressing-Scheme.md`: Breakdown of the subnetting plan and VLAN IP ranges.

## 📸 Expected Simulation Output
The primary output of this simulation is a **fully functional and testable virtual network**. When you run the simulation, you should be able to:
*   **Ping Successfully**: Send pings from any PC to any other device (including across VLANs) and receive replies, visually seeing packets travel through switches and routers.
    ![Successful Ping Test](screenshots/ping-test-successful.png)
*   **View Device Configurations**: Open the command-line interface (CLI) of any router or switch to verify its settings (e.g., `show vlan brief`, `show ip route`).
    ![VLAN Configuration Table](screenshots/vlan-tables.png)
*   **Observe Network Traffic**: In Simulation Mode, watch as packets (PDUs) are built, encapsulated, routed, and delivered, with each step explained in the event list.

## 🔧 Implementation Steps
Follow these steps in Cisco Packet Tracer to build the network from scratch:

### **Phase 1: Topology Design**
1.  Drag and drop devices from the inventory: **Switches** (Layer 2 & 3), **Routers**, **PCs**, and **Servers**.
2.  Connect them using appropriate cables (Copper Straight-Through for switch-to-PC, Copper Cross-Over for switch-to-switch at the distribution layer).
3.  Arrange devices to reflect a **star topology** with a central core.

### **Phase 2: VLAN and Switch Configuration**
1.  On each access layer switch, create VLANs (e.g., 10, 20, 30) and name them.
    ```cisco
    Switch(config)# vlan 10
    Switch(config-vlan)# name Civil_Eng
    ```
2.  Assign access ports to their respective VLANs.
    ```cisco
    Switch(config)# interface FastEthernet0/1
    Switch(config-if)# switchport mode access
    Switch(config-if)# switchport access vlan 10
    ```

### **Phase 3: IP Addressing and Routing**
1.  Configure the **Layer 3 switch** with **Switched Virtual Interfaces (SVIs)** for each VLAN to act as the default gateway.
    ```cisco
    L3_Switch(config)# interface Vlan10
    L3_Switch(config-if)# ip address 192.168.10.1 255.255.255.0
    ```
2.  Enable IP routing on the Layer 3 switch: `L3_Switch(config)# ip routing`.

### **Phase 4: Testing and Validation**
1.  Set all PCs to "DHCP" to receive IP addresses automatically.
2.  Use the `ping` command from the PC's desktop tab to test connectivity.
3.  Use the `tracert` command from the PC's command prompt to trace the path packets take.

## 🤝 Contributing & Future Improvements
Contributions are welcome! Potential future enhancements for this project include:
*   Implementing dynamic routing protocols (e.g., OSPF) between routers.
*   Adding network security with Access Control Lists (ACLs).
*   Integrating wireless LAN controllers and access points.
*   Simulating different types of network traffic (HTTP, FTP, VoIP).
