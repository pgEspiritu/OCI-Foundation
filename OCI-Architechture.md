# 🌐 OCI Architecture Overview

Welcome to this lesson on **Oracle Cloud Infrastructure (OCI) Architecture**. This summary covers the key constructs of OCI's physical architecture: Regions, Availability Domains (ADs), and Fault Domains (FDs).

---

## 📍 Key Concepts

### 🗺️ Region
- A **geographic area** containing one or more **Availability Domains (ADs)**.
- Choose regions based on:
  - **Proximity to users** (lower latency, better performance)
  - **Data residency and compliance** requirements
  - **Service availability**

### 🏢 Availability Domain (AD)
- One or more **fault-tolerant data centers** in a region.
- **Isolated** from each other to prevent cascading failures.
- Do not share infrastructure such as power or cooling.
- Designed to ensure that failure in one AD does not affect others.

### 🧱 Fault Domain (FD)
- Logical groupings within an AD (usually 3 per AD).
- Prevent single points of hardware failure (e.g., physical servers, racks, switches).
- Used for **anti-affinity** and high availability by distributing workloads across domains.
- Can assign compute/database instances to specific FDs at **launch time**.
- Oracle internally leverages FDs to isolate changes and minimize impact.

---

## 🛠️ Designing for High Availability

- **Distribute application tiers** and **databases** across multiple FDs for redundancy.
- Replicate across **multiple ADs** for additional fault tolerance.
- Use technologies like **Oracle Data Guard** to sync data between ADs.
- Even in **single-AD regions**, use FDs to increase availability.

---

## 🔁 Summary (Inside-Out View)

- **Fault Domain**: Protects against local hardware failures within an AD.
- **Availability Domain**: Protects against full AD failure (in multi-AD regions).
- **Region**: Grouping of ADs; supports compliance, disaster recovery, and redundancy.
- **Region Pair**: Most countries have at least 2 regions for disaster recovery and compliance.

---

## 📌 Takeaway

OCI provides architectural constructs (Regions → ADs → FDs) to help design **resilient, fault-tolerant, and highly available** cloud applications. Understanding and leveraging these layers helps avoid single points of failure and ensures compliance with performance and availability SLAs.
