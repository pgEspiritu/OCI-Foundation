# 🖥️ OCI Instance Basics – Summary

## 📌 What is an Instance?
An **instance** in OCI refers to a **compute host**—a virtual machine (VM) or bare metal server—used to run your applications.

---

## 🔗 Key Dependencies

### 1. 🌐 Networking Dependency
- **Region** → contains **Availability Domains (ADs)** → each AD is a physical **data center**.
- Each compute instance must be associated with a **Virtual Cloud Network (VCN)**.
- Within a VCN, you have **subnets** where instances reside.
- Each instance uses a **Virtual NIC (VNIC)** placed in a subnet to get:
  - **Private IP address**
  - Network routing

---

### 2. 💾 Storage Dependency
- Every instance requires:
  - **Boot Volume (OS)**: launched from a **boot disk image** stored in block storage.
  - **Block Volumes (Data)**: additional storage (like file systems) attached as needed.
- Both are part of OCI’s **Block Volume Service**, which provides **remote network-attached storage**.

---

## 🔄 Live Migration

| Feature            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Live Migration** | Automatically moves a VM from one host to another **without rebooting**     |
| **Purpose**         | Keeps your application running during hardware failures or maintenance     |
| **User Control**    | Opt-in/opt-out based on workload preference                                |

> 🛡️ OCI handles host failures or maintenance events **seamlessly**, ensuring high availability with **minimal or no downtime**.

---

## 🧠 Recap
- OCI compute instances rely on **networking (VCN, subnet, VNIC)** and **block storage (boot and data volumes)**.
- **Live Migration** enables seamless operations across hosts with zero manual intervention.

