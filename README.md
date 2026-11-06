# Cycle-1-3-IMPLEMENTATION-OF-LINK-STATE-ROUTING-PROTOCOL-OSPF-
# 🧪 IMPLEMENTATION OF LINK STATE ROUTING PROTOCOL (OSPF)
# NAME : SHIYAM KUMAR S
# REG NO : 212223060260

## 🎯 AIM
To connect computers in multiple networks using Open Shortest Path First (OSPF) Routing Protocol and to verify the connectivity between computers.

---

## 🛠️ EQUIPMENTS REQUIRED

| S.No | Name                 | Quantity |
|------|----------------------|----------|
| 1    | Desktop Computer     | 4        |
| 2    | Cisco 1800 Router    | 2        |
| 3    | DCE-DTE Cable        | 1        |
| 4    | Cisco 2900 Switch    | 2        |
| 5    | CAT 6 Patch Cable    | 6        |
| 6    | Console Cable        | 2        |

---

## 🌐 IP ASSIGNMENT

| Name                     | IP Address     | Subnet Mask     | Network      | Class | Gateway        |
|--------------------------|----------------|-----------------|--------------|-------|----------------|
| PC0                      | 192.168.0.1    | 255.255.255.0   | 192.168.0.0  | C     | 192.168.0.200  |
| PC1                      | 192.168.0.2    | 255.255.255.0   | 192.168.0.0  | C     | 192.168.0.200  |
| PC2                      | 192.168.2.1    | 255.255.255.0   | 192.168.2.0  | C     | 192.168.1.200  |
| PC3                      | 192.168.2.2    | 255.255.255.0   | 192.168.2.0  | C     | 192.168.1.200  |
| Router0 FastEthernet0/0  | 192.168.0.200  | 255.255.255.0   | 192.168.0.0  | C     | —              |
| Router0 Serial2/0        | 192.168.1.1    | 255.255.255.0   | 192.168.1.0  | C     | —              |
| Router1 FastEthernet0/0  | 192.168.2.200  | 255.255.255.0   | 192.168.2.0  | C     | —              |
| Router1 Serial2/0        | 192.168.1.2    | 255.255.255.0   | 192.168.1.0  | C     | —              |

---

## 🗺️ NETWORK DIAGRAM



<img width="1920" height="1080" alt="Screenshot 2026-10-17 104241" src="https://github.com/user-attachments/assets/71b43a77-bb4c-4791-b771-e169dd267f2b" />



## 🧭 PROCEDURE

1. Open Cisco Packet Tracer software.  
2. Drag two 2900 switches, two Cisco 1800 routers, and four PC terminals into the workspace.  
3. Connect all devices using CAT 6 patch cables as per the network diagram.  
4. Configure IP addresses and gateways for all PCs.  
5. Configure Delhi router IP address, save configuration, and restart.  
6. Configure Chennai router IP address, save configuration, and restart.  
7. Check connectivity between computers in the same network.  
8. Configure OSPF on Delhi router, save configuration, and restart.  
9. Configure OSPF on Chennai router, save configuration, and restart.  
10. Verify connectivity between PCs in different networks using the `ping` command.  
11. Check routing tables using `show ip route` on both routers.


## 🔧 ROUTER CONFIGURATION

### Router0 (Delhi)

```bash
Router> enable
Router# configure terminal
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface Serial2/0
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# clock rate 64000
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# router ospf 1
Router(config-router)# router-id 1.1.1.1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# exit
Router# write memory
```
### Router1 (Chennai)
```bash
Router> enable
Router# configure terminal
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface Serial2/0
Router(config-if)# ip address 192.168.2.2 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# router ospf 1
Router(config-router)# router-id 2.2.2.2
Router(config-router)# network 192.168.3.0 0.0.0.255 area 0
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# exit
Router# write memory
```
## 🔍 VERIFICATION
Check OSPF Neighbors
```bash
Router0# show ip ospf neighbor
```
Check Routing Table
```bash
Router0# show ip route
Router1# show ip route
```
## 📤 OUTPUT

<img width="1920" height="1080" alt="Screenshot 2026-10-17 104135" src="https://github.com/user-attachments/assets/1a9a711d-3f64-4513-91c7-e2270302ead0" />

<img width="1920" height="1080" alt="Screenshot 2026-10-17 104214" src="https://github.com/user-attachments/assets/cabcb061-d611-4fdf-9fa3-3382d55e7fa7" />

<img width="1920" height="1080" alt="Screenshot 2026-10-17 104045" src="https://github.com/user-attachments/assets/a755e4f0-750d-4a44-bac3-e4f5be2096c7" />



## 📝 RESULT
Thus, the computers in multiple networks using Open Shortest Path First (OSPF) Routing Protocol are successfully connected and the connectivity between them is verified.
