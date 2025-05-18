# Office Network Design – Cisco Packet Tracer

This project simulates a small office network designed using Cisco Packet Tracer 8.2, focusing on IP subnetting, device planning, and static routing without VLANs or CLI configuration.

---

## Project Objectives

- Practice Network+ level subnetting and topology design
- Allocate IP addresses efficiently with room for expansion
- Use static routing for inter-department communication
- Validate connectivity through Ping and ICMP analysis

---

## 🧱 Network Overview

IP ranges were calculated based on:
- C = Current devices
- F = Future devices (reserved)
- G = 1 IP reserved for Default Gateway

| Dept   | C | F | G | Total IPs | Subnet Mask        | Subnet ID       | Host IP Range             | Broadcast         |
|--------|---|---|---|-----------|---------------------|------------------|---------------------------|-------------------|
| Mgmt   | 3 | 3 | 1 | 7         | 255.255.255.240 (/28) | 192.168.10.0     | 192.168.10.1 – .14        | 192.168.10.15     |
| IT     | 6 | 2 | 1 | 9         | 255.255.255.240 (/28) | 192.168.10.16    | 192.168.10.17 – .30       | 192.168.10.31     |
| HR     | 3 | 1 | 1 | 5         | 255.255.255.248 (/29) | 192.168.10.32    | 192.168.10.33 – .38       | 192.168.10.39     |
| Fin    | 3 | 2 | 1 | 6         | 255.255.255.248 (/29) | 192.168.10.40    | 192.168.10.41 – .46       | 192.168.10.47     |
| Guest  | 2 | 1 | 1 | 4         | 255.255.255.248 (/29) | 192.168.10.48    | 192.168.10.49 – .54       | 192.168.10.55     |
| Server | 2 | 2 | 1 | 5         | 255.255.255.248 (/29) | 192.168.10.56    | 192.168.10.57 – .62       | 192.168.10.63     |

---
