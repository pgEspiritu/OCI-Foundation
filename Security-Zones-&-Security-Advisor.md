# 🔐 OCI Security Zones & Security Advisor

This lesson explores **Security Zones** and **Security Advisor**, two key components of Oracle Cloud Infrastructure's (OCI) security framework.

---

## 🛡️ What Are Security Zones?

- **Security Zones** define compartments where **security cannot be disabled**.
- You assign a compartment (e.g., `Compartment B`) as a **Security Zone**.
- Once designated, **Security Zone Recipes** (sets of security policies) are automatically enforced.

### 🔒 Policy Enforcement Examples

- **Networking**: Subnets must be private. Creating a public subnet = ❌ denied.
- **Encryption**: Only **customer-managed encryption keys** allowed. Violations = ❌ denied.
- **Core Services Supported**:
  - Networking
  - Storage
  - Compute
  - Databases

> 🏠 **Analogy**: Just like you store valuables in a fire-safe vault at home, you store your most critical cloud resources in a Security Zone.

---

## 🧠 What Is Security Advisor?

- **Security Advisor** is a **unified service** combining:
  - Security Zones
  - Cloud Guard
  - Additional OCI security features

### ✅ What It Does:

- Provides **best practice guidance** for securely configuring services.
- Enforces **secure-by-default** setups (e.g., object storage buckets **must not be public**).
- Walks you through tasks like:
  - Creating secure buckets
  - Enabling encryption with customer-managed keys
  - Ensuring resources comply with **Security Zone policies**

### 🔧 Services Supported

- **Object Storage**
- **File Storage**
- **Block Volume**
- **Virtual Machines**

---

## 📝 Summary

| Feature          | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Security Zone** | A designated compartment where security policies cannot be violated         |
| **Security Advisor** | A unified security tool combining Cloud Guard, Security Zone, and more     |

- Use **Security Zones** for high-security compartments.
- Use **Security Advisor** for guided security posture and compliance.
