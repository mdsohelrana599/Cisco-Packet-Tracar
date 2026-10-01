# Cisco Packet Tracer Networking Project

## 📌 Project Overview

This project is created using **Cisco Packet Tracer** to practice and demonstrate basic networking concepts, including VLANs, Router-on-a-Stick, trunking, IP addressing, and inter-VLAN communication.

The main goal of this project is to understand how different VLANs communicate with each other through a router.

---

## 🛠️ Technologies & Tools

* Cisco Packet Tracer
* Cisco Router
* Cisco Switch
* VLAN
* Trunking
* Router-on-a-Stick
* IPv4 Addressing
* Inter-VLAN Routing
* CLI Configuration

---

## 🌐 Network Configuration

### VLAN 10

```text
VLAN ID: 10
Network: 192.168.10.0/24
Gateway: 192.168.10.1
```

### VLAN 20

```text
VLAN ID: 20
Network: 192.168.20.0/24
Gateway: 192.168.20.1
```

---

## 🔧 Router Configuration

The router uses sub-interfaces to provide communication between different VLANs.

Example:

```bash
enable
configure terminal

interface fa0/0
no shutdown

interface fa0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
no shutdown

interface fa0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
no shutdown
```

---

## 🔀 Switch Configuration

Example VLAN configuration:

```bash
enable
configure terminal

vlan 10
name VLAN10

vlan 20
name VLAN20
```

Access ports can then be assigned to the appropriate VLAN.

Example:

```bash
interface fa0/1
switchport mode access
switchport access vlan 10
```

For the router connection, the switch port should be configured as a trunk:

```bash
interface fa0/24
switchport mode trunk
```

---

## 📡 Network Topology

```text
             +----------------+
             |     Router     |
             |    Fa0/0       |
             +-------+--------+
                     |
                   Trunk
                     |
             +-------+--------+
             |     Switch     |
             +---+--------+---+
                 |        |
              VLAN 10   VLAN 20
                 |        |
              PCs       PCs
```

---

## 🎯 Learning Objectives

Through this project, I practiced:

* Creating VLANs
* Assigning switch ports to VLANs
* Configuring trunk ports
* Creating router sub-interfaces
* Configuring `encapsulation dot1Q`
* Assigning IP addresses
* Configuring default gateways
* Understanding Inter-VLAN Routing
* Testing network connectivity using `ping`
* Working with Cisco IOS CLI commands

---

## 🧪 Testing

After completing the configuration, connectivity can be tested using:

```bash
ping 192.168.10.1
ping 192.168.20.1
```

The `show` commands can also be used to verify the configuration:

```bash
show vlan brief
show interfaces trunk
show ip interface brief
show running-config
```

---

## 📁 Project File

The Cisco Packet Tracer project file is:

```text
Cisco-Packet-Tracer-Project.pkt
```

Open the `.pkt` file using **Cisco Packet Tracer** to view the complete network topology and configuration.

---

## 👨‍💻 Author

**Md Sohel Rana**

Frontend Developer | Networking Learner

---

## ⭐ Purpose

This project is part of my networking practice and learning journey. It helps build practical knowledge of Cisco networking, VLANs, trunking, and inter-VLAN routing.
