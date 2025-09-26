# Cisco HSRP Lab

## 📌 Overview
This lab demonstrates the configuration of Hot Standby Router Protocol (HSRP) for redundancy in Cisco routers. HSRP ensures high availability by configuring two routers to act as a single virtual default gateway for hosts in the LAN.

## 🛠 Lab Topology
- **R1**: 192.168.1.1/24 (HSRP Active)
- **R2**: 192.168.1.2/24 (HSRP Standby)
- **Virtual IP**: 192.168.1.254 (Default Gateway for PCs)

## ⚙ Configuration

### R1
```bash
interface g0/0
 ip address 192.168.1.1 255.255.255.0
 standby 1 ip 192.168.1.254
 standby 1 priority 110
 standby 1 preempt
 no shutdown

### R2
```bash
interface g0/0
 ip address 192.168.1.2 255.255.255.0
 standby 1 ip 192.168.1.254
 standby 1 priority 90
 standby 1 preempt
 no shutdown
