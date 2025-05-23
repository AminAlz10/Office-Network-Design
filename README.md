# Office Network Design – Cisco Packet Tracer

This project simulates a small office network designed using Cisco Packet Tracer 8.2, focusing on IP subnetting, device planning, and static routing without VLANs or CLI configuration.

---

## Project Objectives

- Practice Network+ level subnetting and topology design
- Allocate IP addresses efficiently with room for expansion
- Use static routing for inter-department communication
- Validate connectivity through Ping and ICMP analysis

---
## IP Design Decisions

- **Private IP Range (192.168.10.0/24)** was chosen as it's ideal for internal office LANs.
- Subnets were manually calculated to **minimize IP waste** and support **future scalability**.
- Routers were assigned addresses from **10.0.0.0/30** range (e.g. `10.0.0.1`, `10.0.0.2`) to simulate WAN-like connections between router interfaces — this is a **commonly used point-to-point range** in practice.
- DHCP was intentionally **not used**, to ensure **static control** over addressing and reinforce manual subnetting concepts (as expected at Network+ level).


## Network Overview

IP ranges were carefully calculated for each department based on:
- Current number of devices
- Reserved IPs for **future expansion**
- Inclusion of 1 IP per subnet for the **default gateway**

Abbreviations:
- C = Current devices
- F = Future devices (reserved)
- G = 1 IP reserved for Default Gateway
- C = Current Devices
- F = Future Reserved Devices
- G = Gateway
- Dept = Department
- Mgmt = Management
- Fin = Finance
- Guest = Guest Wi-Fi
- Server = Server Room

This ensures scalability and avoids renumbering when adding new devices.

| Dept   | C | F | G | Total IPs | Subnet Mask        | Subnet ID       | Host IP Range             | Broadcast         |
|--------|---|---|---|-----------|---------------------|------------------|---------------------------|-------------------|
| Mgmt   | 3 | 3 | 1 | 7         | 255.255.255.240 (/28) | 192.168.10.0     | 192.168.10.1 – .14        | 192.168.10.15     |
| IT     | 6 | 2 | 1 | 9         | 255.255.255.240 (/28) | 192.168.10.16    | 192.168.10.17 – .30       | 192.168.10.31     |
| HR     | 3 | 1 | 1 | 5         | 255.255.255.248 (/29) | 192.168.10.32    | 192.168.10.33 – .38       | 192.168.10.39     |
| Fin    | 3 | 2 | 1 | 6         | 255.255.255.248 (/29) | 192.168.10.40    | 192.168.10.41 – .46       | 192.168.10.47     |
| Guest  | 2 | 1 | 1 | 4         | 255.255.255.248 (/29) | 192.168.10.48    | 192.168.10.49 – .54       | 192.168.10.55     |
| Server | 2 | 2 | 1 | 5         | 255.255.255.248 (/29) | 192.168.10.56    | 192.168.10.57 – .62       | 192.168.10.63     |

---
## Configuration Summary

- **Software:** Cisco Packet Tracer v8.2  
- **Routers:** 2 × 2811  
- **Switches:** 6 × 2960-24TT  
- **Cabling:** Straight & Cross  
- **Addressing:** Manual (no DHCP)  
- **Routing:** Static routes (GUI-based)  
- **VLAN:** Not used  
- **CLI:** Not used (GUI only)

---
## Why did I choose these Routers/Switches/Topology?
- **Routers:** Cisco 2811 was selected as a standard general-purpose router often used in Packet Tracer for basic routing labs.
- **Switches:** 2960-24TT switches were chosen for their simplicity and availability in Packet Tracer – no Layer 3 features were needed.
- **Topology:** A **star-based topology** was used to clearly separate departments, simplify routing paths, and ease future upgrades.

## Design Rationale

- Manual IP configuration helped me understand and reinforce concepts of subnet size, IP planning, and broadcast boundaries.
- Avoided DHCP to ensure full visibility and control of IP allocation during learning phase.
- Chose future-ready subnets (e.g., /28 instead of /30) to avoid renumbering as devices grow.
- WAN-style point-to-point IPs (10.0.0.0/30) on routers for realism in inter-router links.


## Testing & Validation

- **Real-Time Mode:** All devices successfully pinged each other
- **Simulation Mode:** Manual ICMP packets traversed the network as expected

### Successful Ping From pc3 in Router0 to Pc 15 in Router2
<img src="Images/8.png" width="500" align="center"/>
### Simulation Mode
<img src="Images/6.png" width="500" align="center"/>

---

## Static Routing Configuration

### Router0
<img src="Images/10.png" width="500"/>

### Router2
<img src="Images/9.png" width="500"/>

---

## Subnetting Work Samples

Manually calculated and documented on paper:

<img src="Images/11.jpg" width="400"/>

----------------------------------------
<img src="Images/13.jpg" width="400"/>

-----------------------------------------
<img src="Images/14.jpg" width="400"/>


---

## Full Network Topology

<img src="Images/1.png" width="700"/>

---

## Lessons Learned

- Even small subnet miscalculations can break the topology
- Planning for future devices avoids reconfiguring subnets
- Debugging routing requires patience and careful gateway setup
- Manual ping testing is essential when simulation isn’t automatic

---

## Target Audience

This project is suitable for students and beginners preparing for the **Network+** certification or early-stage **CCNA** learners who are exploring network fundamentals.

## 📁 Project File

The complete Cisco Packet Tracer project file can be downloaded below:

🔗 [Download Packet Tracer File](https://github.com/AminAlz10/Office-Network-Design/raw/refs/heads/main/ProjectFile/company.pkt)


