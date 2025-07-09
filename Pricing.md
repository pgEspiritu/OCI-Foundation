# 🧾 OCI Governance and Administration: Pricing Overview

Welcome to this module on **Governance and Administration**. In this lesson, we'll explore **Oracle Cloud Infrastructure (OCI) pricing**.

## ✅ OCI Pricing Models

### 1. **Pay As You Go (PAYG)**
- Usage-based billing.
- No upfront commitment or minimum service period.
- Metered billing for most resources.

**🟰 Equivalent Services:**
- **AWS:** On-Demand Pricing  
- **GCP:** Pay-as-you-go Billing

---

### 2. **Consumption-Based Pricing**
- Applies to services like **OCI Functions**.
- You are charged only when the function runs.
- Ideal for serverless workloads with intermittent activity.

**🟰 Equivalent Services:**
- **AWS:** AWS Lambda  
- **GCP:** Cloud Functions

---

### 3. **Annual Universal Credits**
- Prepaid annual commitment.
- Offers significant discounts based on deal size and term.
- Additional usage is charged at PAYG rates.

**🟰 Equivalent Services:**
- **AWS:** Enterprise Discount Program (EDP)  
- **GCP:** Committed Use Contracts

---

### 4. **Bring Your Own License (BYOL)**
- Use your existing on-prem Oracle licenses in the cloud.
- Reduces overall software costs.

**🟰 Equivalent Services:**
- **AWS:** License Mobility (for Windows/SQL Server)  
- **GCP:** Sole-tenant nodes or BYOL options

---

## 💡 Key Pricing Factors

### 🔹 Size of Resource
- Larger compute/storage resources = higher cost.

### 🔹 Resource Type
- VM vs Bare Metal vs Serverless = different pricing tiers.

### 🔹 Data Transfer
- **Inbound data:** Free (Industry standard)
- **Outbound data:** Up to **10× cheaper** than other providers
- **Intra-AD traffic:** Free on OCI  
  > *Other clouds often charge for inter-AZ/AD data transfers.*

---

## 🌍 Global Uniform Pricing

- OCI has **consistent pricing globally** across all regions.
- No regional price variation, unlike AWS and GCP.

---

## 🧠 Summary

- OCI supports:
  - **Pay As You Go**
  - **Consumption-Based**
  - **Annual Universal Credits**
  - **Bring Your Own License (BYOL)**
- **Transparent**, **simple**, and **globally consistent** pricing.
- OCI data transfer rates are significantly lower than AWS and GCP.
