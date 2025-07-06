# 🛠️ OCI VCN Wizard Demo

In this demo, we will create a **Virtual Cloud Network (VCN)** using the **OCI VCN Wizard**.

## 🌐 Topology Overview

We will create the following:
- A **VCN** in the `sandbox` compartment
- One **Public Subnet**
- One **Private Subnet**
- The following **Gateways**:
  - Internet Gateway
  - NAT Gateway
  - Service Gateway

---

## 🧭 Step-by-Step Instructions

### ✅ Step 1: Open the OCI Console
- Log in to the [OCI Console](https://cloud.oracle.com/).
- Open the **Navigation Menu** (☰) > **Networking** > **Virtual Cloud Networks**.

### ✅ Step 2: Launch the VCN Wizard
- Click **Create VCN with Internet Connectivity** (simpler option).
- Click **Start VCN Wizard**.

### ✅ Step 3: Provide VCN Details
- **Name:** `VCN-US-East-Demo`
- **Compartment:** `sandbox`
- **CIDR Block:** `10.0.0.0/16` (default)
- **Subnets:**
  - Public Subnet: `10.0.0.0/24`
  - Private Subnet: `10.0.1.0/24`

> ℹ️ You can change the default CIDR values if needed. Use a [CIDR calculator](https://www.ipaddressguide.com/cidr) for custom subnetting.

### ✅ Step 4: Review and Create
- Review the list of components to be created:
  - 1 VCN
  - 2 Subnets
  - 2 Route Tables
  - 2 Security Lists
  - 3 Gateways (Internet, NAT, Service)
- Click **Create**.

---

## 🧩 Post-Creation Overview

After creation, click **View VCN** to explore:

| Component         | Details |
|------------------|---------|
| Subnets          | Public + Private |
| Route Tables     | One for each subnet |
| Security Lists   | Separate for each subnet |
| Gateways         | Internet Gateway, NAT Gateway, Service Gateway |

---

## 🗺️ Visualizing the VCN

### 🧭 Use the Network Visualizer
- Navigate to **Network Command Center** > **Network Visualizer**
- View a graphical representation of your VCN:
  - **Public Subnet** routes through **Internet Gateway**
  - **Private Subnet** routes through **NAT Gateway** and **Service Gateway**

### 🛰️ Routing Map Summary

| Subnet         | Internet Access         | Typical Use Case       |
|----------------|--------------------------|-------------------------|
| Public Subnet  | ✅ Internet Gateway       | Web Servers             |
| Private Subnet | ✅ NAT / Service Gateway | Databases, Backend Apps |

---

## ✅ Recap

- Created a **VCN with public and private subnets** using the **VCN Wizard**
- Automatically provisioned:
  - Gateways
  - Route Tables
  - Security Lists
- Verified setup using **Network Visualizer**

> 🎯 This setup forms the foundation for launching compute instances and enabling secure networking in OCI.

---

## 📚 Resources

- [VCN Overview – Oracle Docs](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm)
- [CIDR Notation Guide](https://www.cloudflare.com/learning/network-layer/what-is-cidr/)
