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

### OCID Format:
