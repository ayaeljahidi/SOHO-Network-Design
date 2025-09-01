# 🏢 SOHO Network Design (Cisco Packet Tracer)

[![Cisco](https://img.shields.io/badge/Cisco-PacketTracer-1BA0D7?logo=cisco&logoColor=white)]()  
[![CCNA](https://img.shields.io/badge/CCNA-Networking-1E90FF?logo=cisco&logoColor=white)]()  
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)]()  
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)]()  

This project demonstrates the design and implementation of a **Small Office/Home Office (SOHO) Network** using **Cisco Packet Tracer**.  

---

## 📌 Project Requirements

- ✅ One **router** and one **switch** (Cisco products)  
- ✅ **3 Departments**:  
  - Admin/IT (VLAN 10)  
  - Finance/HR (VLAN 20)  
  - Customer Service/Reception (VLAN 30)  
- ✅ Each department must be in a **separate VLAN**  
- ✅ Each department must have **wireless access**  
- ✅ Hosts must **obtain IPv4 addresses automatically** via DHCP  
- ✅ Devices in all VLANs must **communicate with each other** (Router-on-a-Stick)  
- ✅ Base network: `192.168.1.0/24`

---

## 🖥️ VLAN & IP Allocation Table

| Department                   | VLAN | Subnet             | Gateway        | Range of IPs         |
|-------------------------------|------|-------------------|----------------|----------------------|
| Admin / IT                   | 10   | 192.168.1.0/26    | 192.168.1.1    | 192.168.1.2 → .62    |
| Finance / HR                 | 20   | 192.168.1.64/26   | 192.168.1.65   | 192.168.1.66 → .126  |
| Customer Service / Reception | 30   | 192.168.1.128/26  | 192.168.1.129  | 192.168.1.130 → .190 |

---

## 🔧 Configuration Highlights

### VLAN & Router-on-a-Stick Example
```bash
int g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.1.65 255.255.255.192
