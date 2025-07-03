# 🌐 OCI Networking Introduction

Welcome to this module on **OCI Networking**.

## 🧩 What is a Virtual Cloud Network (VCN)?

A **Virtual Cloud Network (VCN)** is a **private, software-defined network** you create in Oracle Cloud Infrastructure (OCI). It's used for **secure communication** across various environments:

- Between OCI instances
- Between OCI and on-premises environments
- Between OCI regions

> ✅ **VCN is a regional service** – meaning it is created within a specific OCI region.

---

## 🗺️ Address Space and Subnetting

- Each VCN has a **CIDR block** (e.g., `10.0.0.0/16`)
- This CIDR range is **subnetted** into smaller networks
  - Example:
    - `10.0.1.0/24` → Public Subnet
    - `10.0.2.0/24` → Private Subnet
- Compute instances are launched into these **subnets**
  - Each instance gets a **private IP address** for communication

---

## 🌐 Communication Mechanisms within a VCN

### 1. **Internet Gateway**
- Enables **two-way communication** with the internet
- Used for **public-facing** resources (e.g., web servers)

### 2. **NAT Gateway**
- Enables **outbound traffic only** from private subnets to the internet
- **Inbound internet connections are blocked**
- Ideal for patching or downloading from the internet securely

### 3. **Service Gateway**
- Enables **private access** to Oracle services like **Object Storage**
- **No public internet traffic** involved

### 4. **Dynamic Routing Gateway (DRG)**
- Enables **private network connectivity** with:
  - **On-premises environments**
  - **Other VCNs** (via VPN or FastConnect)

---

## 🔁 Recap

- A **VCN** is your customizable virtual network in OCI.
- It is **secure, scalable, and highly available**.
- Supports multiple **gateway types** for internal, external, and hybrid communication.

---

📘 *This is a foundational lesson. Deeper dives into VCN components and configurations will follow in subsequent modules.*
