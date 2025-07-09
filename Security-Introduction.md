# 🔐 OCI Security Module

Welcome to this module on **Oracle Cloud Infrastructure (OCI) Security**. This lesson introduces the **shared security model** and outlines how **OCI implements security using a defense-in-depth strategy** across various layers of the cloud stack.

---

## 📌 Introduction to the Shared Security Model

### 🏢 On-Premises Security
In traditional on-premises environments, **you are responsible for the entire technology stack**:
- Physical infrastructure
- Network and hardware
- Software and data
- Identity and access management

You **own and manage everything**—security is your full responsibility.

### ☁️ Cloud Security: Shared Responsibility
When you move to the cloud, **security responsibilities are shared** between you and the cloud provider (Oracle in this case):

| Responsibility                    | Oracle (OCI)             | You (Customer)                            |
|----------------------------------|--------------------------|-------------------------------------------|
| Physical data centers            | ✅ Yes                   | ❌ No                                     |
| Physical network & hosts         | ✅ Yes                   | ❌ No                                     |
| Virtualization infrastructure    | ✅ Yes                   | ❌ No                                     |
| OS patching & configuration      | ❌ Optional (You manage) | ✅ Yes                                     |
| Identity & Access Management     | ❌                      | ✅ Yes                                     |
| Data security                    | ❌                      | ✅ Yes                                     |
| Devices, endpoints               | ❌                      | ✅ Yes                                     |

This division of labor is known as the **Shared Security Model**:
- Oracle secures **_the cloud_**
- You secure **_what you run in the cloud_**

---

## 🧱 OCI Defense-In-Depth Security Model

OCI applies a **defense-in-depth** approach, meaning security is layered across the full stack. Here’s how it's structured:

### 🔐 Use Case-Based Security Services

We will go through these layers one by one, with representative services and use cases for each.

---

## 1️⃣ Infrastructure Protection

These services protect your **cloud network, applications, and perimeter**:

- **Web Application Firewall (WAF)**  
  Protects applications from unwanted or malicious internet traffic.  
  Mitigates Layer 7 (Application Layer) DDoS attacks.

- **Network Firewall**  
  Monitors traffic across your virtual cloud network (VCN).  
  Supports intrusion detection and prevention.

---

## 2️⃣ Identity and Access Management (IAM)

Manages **who** can access **what**, and **how much** access they have:

- **IAM Service**  
  Define users, groups, policies, and compartments.

- **Multi-Factor Authentication (MFA)**  
  Adds an extra layer of identity verification beyond usernames/passwords.

- **Identity Federation & SSO**  
  Supports federating OCI access with other identity providers (IdPs).

---

## 3️⃣ OS and Workload Protection

These services protect your **virtual machines and operating environments**:

- **Shielded Instances**  
  Offer secure VMs with features like Secure Boot to only run trusted software.

- **Dedicated VM Hosts**  
  Bare metal hosts that are single-tenant and fully dedicated to you.

- **OS Management Service**  
  Automates patching, updates, and monitoring for large-scale OS fleets.

---

## 4️⃣ Data Protection

Critical for ensuring **confidentiality, integrity, and availability of your data**:

- **Vault**  
  Manages encryption keys and secrets (passwords, tokens, API keys).

- **Certificates Service**  
  Enables lifecycle management of SSL/TLS certificates and custom Certificate Authorities (CAs).

---

## 5️⃣ Detection and Remediation

Also known as **Cloud Security Posture Management (CSPM)**. Focuses on **monitoring and automatic remediation**:

- **Cloud Guard**  
  Continuously monitors for misconfigurations or suspicious activity.  
  Provides automated responses to threats.

- **Security Zones**  
  Enforce OCI-defined security policies at the compartment level.  
  Examples:  
  - Block public access to sensitive resources  
  - Require encryption  
  - Prevent creation of non-compliant resources

---

## 🧭 Example: How These Services Work Together

In a typical OCI environment, you may use a combination of the following:
- **Virtual Cloud Network (VCN)** to isolate workloads
- **IAM** to manage access to cloud resources
- **Vault** for secure key and secret management
- **Bastion** for secure SSH access to private compute instances
- **Audit** for tracking all activities
- **Vulnerability Scanning** to identify risks
- **Cloud Guard & Security Zones** for posture management

---

## 🔁 Summary

- In OCI, **security is a shared responsibility** between Oracle and you.
- OCI applies **defense-in-depth**—security at every layer of the stack.
- OCI offers a comprehensive **security portfolio** tailored to various use cases:
  - Infrastructure protection
  - Identity and access management
  - OS and workload protection
  - Data protection
  - Detection and remediation

---

## 🚀 What’s Next?

In upcoming modules, we’ll dive deeper into:
- Configuring IAM
- Setting up WAF and firewalls
- Using Vault and Security Zones
- Implementing Cloud Guard policies
- Best practices for OS patching and key management

Stay tuned for a deeper exploration into each of these security features!
