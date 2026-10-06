# Routing Protocol Labs: RIP, OSPF, BGP (Cisco Packet Tracer)

Hands-on labs from my **CCNA** course on dynamic routing, built in **Cisco Packet Tracer 9.0**.


## Labs at a Glance

| # | Lab | Topic | Routers | Switches | PCs |
| --- | --- | --- | --- | --- | --- |
| 1 | [RIP Lab](#1-rip-lab) | Distance-vector routing | 2 | 2 | 4 |
| 2 | [OSPF Lab](#2-ospf-lab) | Link-state routing | 2 | 2 | 4 |
| 3 | [BGP Lab](#3-bgp-lab) | Path-vector routing | 2 | 2 | 4 |
| 4 | [Three-Router Lab (Task 1)](#4-three-router-lab-task-1) | Multi-router routing with multiple LANs | 3 | 3 | 12 |

## Tools Used

- Cisco Packet Tracer 9.0
- Cisco ISR 4321 / 4331 / 2911 routers
- Cisco 2960-24TT switches
- PC-PT end devices

---

## 1. RIP Lab

**Objective:** Configure RIP so two separate LANs can communicate through two routers.

![RIP Lab](images/rip-lab.png)

| Network | Subnet |
| --- | --- |
| Router-to-router link | 10.10.1.0/24 (`.4` and `.5`) |
| LAN A (Router0) | 172.16.10.0/24, gateway `172.16.10.1` |
| LAN B (Router1) | 192.168.20.0/24, gateway `192.168.20.1` |

Hosts: PC0 `172.16.10.4`, PC1 `172.16.10.5`, PC2 `192.168.20.4`, PC3 `192.168.20.5`.

**Verification:** Ping between PCs in different LANs; `show ip route` should list `R` (RIP) routes.

---

## 2. OSPF Lab

**Objective:** Configure OSPF between two routers so that PCs on both LANs can reach each other.

![OSPF Lab](images/ospf-lab.png)

Topology: two routers connected on `Gig0/0/1`, each connected to a 2960 switch (`Gig0/0/0` to `Fa0/3`) with two PCs per switch.

**Verification:** `show ip ospf neighbor`, `show ip route` (look for `O` routes), and pings between PCs.

---

## 3. BGP Lab

**Objective:** Establish a BGP peering between two routers and exchange LAN routes.

![BGP Lab](images/bgp-lab.png)

Topology: two ISR 4321 routers connected on `Gig0/0/1`, each with a switch and two PCs on its LAN.

**Verification:** `show ip bgp summary`, `show ip route` (look for `B` routes), and pings between PCs.

---

## 4. Three-Router Lab (Task 1)

**Objective:** Connect three routers in a triangle and route between six LAN subnets.

![Task 1](images/task1-three-router-lab.png)

| Link | Subnet |
| --- | --- |
| Router A – Router B | 20.10.0.0/24 (`.4` / `.5`) |
| Router A – Router C | 40.30.10.0/24 (`.4` / `.5`) |
| Router B – Router C | 30.20.10.0/24 (`.4` / `.5`) |

| Switch | Subnets |
| --- | --- |
| Switch0 | 172.16.10.0/24, 172.16.20.0/24 |
| Switch1 | 10.1.1.0/24, 10.20.5.0/24 |
| Switch2 | 192.168.10.0/24, 192.168.20.0/24 |

---

## Useful Commands

```
show ip route
show ip interface brief
show ip protocols
show ip ospf neighbor
show ip bgp summary
show running-config
ping <ip-address>
traceroute <ip-address>
```

## Skills Demonstrated

- Static and dynamic routing (RIP, OSPF, BGP)
- IP addressing and subnetting
- Router and switch CLI configuration
- Network troubleshooting with ping, traceroute, and `show` commands

## Author

**Lavanya** – CCNA course labs
