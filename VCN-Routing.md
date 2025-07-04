# 🚦 OCI Routing Overview

Welcome to this lesson on **OCI Routing**.

## 🧭 What is a Route Table?

A **route table** in OCI is used to direct outbound traffic **from a subnet** to:
- The internet
- On-premises networks
- Peered VCNs

### 📌 Route Table Components
- **Route Rule** = Destination CIDR Block + Route Target (Next Hop)

> ⚠️ No route rule is needed for traffic within the **same VCN** – OCI handles **intra-VCN communication** automatically.

---

## 🛣️ Example: Routing from a Private Subnet

### 🔁 Scenario:
- **Private subnet** needs to:
  - Get patches from the **internet** (via **NAT Gateway**)
  - Resolve DNS from **on-premises** (via **DRG**)

### 📋 Route Table Entries:
| Destination CIDR | Target         |
|------------------|----------------|
| `0.0.0.0/0`      | NAT Gateway    |
| `172.16.0.0/16`  | DRG (On-prem)  |

> 🎯 OCI uses **longest prefix match**: `/16` is more specific than `/0`, so traffic to `172.16.0.0/16` goes to DRG, everything else goes to the internet.

---

## 🌐 Peering VCNs

VCNs in the same or different regions can communicate via **peering**.

### 🔗 Types of Peering

1. **Local Peering (Same Region)**
   - Uses **Local Peering Gateway (LPG)**
   - Enables private traffic within the region

2. **Remote Peering (Different Regions)**
   - Uses **Dynamic Routing Gateway (DRG)**
   - Routes traffic across OCI regions

---

## 🧩 Scaling with DRG v2

When managing **large VCN environments** (e.g., 10 to 300 VCNs), using **LPGs** for each pair becomes unmanageable.

### 💡 Solution: DRG v2
- Eliminates point-to-point LPG setup
- Allows **up to 300 VCNs** to connect via **a single DRG**
- Supports remote peering to other DRGs for scaling beyond 300 VCNs

> DRG v2 simplifies complex topologies and makes multi-VCN connectivity scalable and maintainable.

---

## ✅ Recap

- **VCN route tables** direct traffic from subnets to NAT, DRG, LPG, and other targets.
- **Longest prefix match** determines which rule applies.
- **Local and remote peering** enable inter-VCN communication.
- **DRG v2** is recommended for scalable multi-VCN architecture.
