# 🔐 OCI Identity and Access Management (IAM) Overview

This lesson provides a high-level overview of **Oracle Cloud Infrastructure (OCI) Identity and Access Management (IAM)**. OCI IAM enables **secure and controlled access** to cloud resources.

---

## 🔑 What is IAM?

**IAM** (Identity and Access Management) is Oracle’s service for managing:
- **Authentication (AuthN):** Verifying *who* a user is.
- **Authorization (AuthZ):** Defining *what* a user is allowed to do.

OCI IAM enforces fine-grained and role-based access control, ensuring that only authorized users can access specific resources.

---

## ⚙️ Key Components

### 🔐 Authentication (AuthN)
- Validates identity using common mechanisms (e.g., username & password).
- Ensures users are who they claim to be.

### ✅ Authorization (AuthZ)
- Determines what authenticated users are permitted to do.
- Users are assigned to **roles**, and each role has **policies** defining permissions.

---

## 📦 IAM Concepts & Features

### 🧱 Identity Domain
- A **container** for users and groups.
- Represents a user population and its associated security configurations.
- Users and groups are created **within** an identity domain.

### 👥 Principals
- Entities (e.g., users, groups, dynamic groups) that **request access** to resources.

### 🗂️ Compartments
- Logical containers used to **isolate and organize** cloud resources.
- Policies are **scoped** to compartments or tenancies.

---

## 📜 Policies
- Define **what actions** a group of users can perform on which resources.
- Example: `Allow group Admins to manage all-resources in tenancy`

---

## 🆔 Oracle Cloud Identifier (OCID)
Every OCI resource is automatically assigned a globally unique identifier called an **OCID**.

### OCID Format: ocid1.<resource-type>.<realm>.<region>.<unique-id>


### 🔎 OCID Components:
- `resource-type`: Type of resource (e.g., `instance`, `blockvolume`)
- `realm`: Group of regions with the same governance (e.g., commercial, government)
- `region`: Region where the resource resides
- `unique-id`: Oracle-generated string uniquely identifying the resource

### Example OCIDs:
- **Tenancy:** `ocid1.tenancy.oc1..<unique-id>` (no region info since it's global)
- **Block Volume:** `ocid1.volume.oc1.phx.<unique-id>` (region-specific)

---

## 🛠️ Usage
- **Console users** rarely see or use OCIDs.
- **CLI and SDK users** frequently reference OCIDs to manage resources programmatically.

---

## 🧾 Summary

| Concept        | Description                                     |
|----------------|-------------------------------------------------|
| IAM            | Manages identity and access to OCI resources    |
| Authentication | Verifies *who* a user is                        |
| Authorization  | Determines *what* a user can do                 |
| Identity Domain| Container for user/group management             |
| OCID           | Unique identifier for each OCI resource         |
| Policies       | Control access based on groups and compartments |

---

OCI IAM provides the foundational security layer for managing access to all cloud resources. By understanding and properly configuring authentication, authorization, and identity domains, you can design a **secure and well-governed cloud environment**.

*Thanks for reading! More IAM topics like policies, dynamic groups, and compartments will be explored in future lessons.*

