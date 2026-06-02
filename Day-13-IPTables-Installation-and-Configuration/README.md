# Day 13 - IPTables Installation and Configuration

## 📌 Overview
This project demonstrates how to secure Linux application servers using iptables firewall rules. The goal is to restrict access to Apache running on port 3000 so that only the Load Balancer (LBR) can access it, while blocking all other external traffic.

---

## 🎯 Objective
- Install and configure iptables on all application servers
- Allow only Load Balancer (LBR) access to port 3000
- Block all other traffic to port 3000
- Ensure firewall rules persist after system reboot

---

## 🏗️ Infrastructure Details
- **OS:** CentOS Stream 9
- **Application Servers:** stapp01, stapp02, stapp03
- **Load Balancer:** stlb01
- **Application Port:** 3000 (Apache Web Server)

---

## ⚙️ Implementation Steps

### 1. Install iptables services
Installed firewall packages on all application servers.

```bash
yum install -y iptables iptables-services
