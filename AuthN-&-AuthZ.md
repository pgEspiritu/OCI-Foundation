# 🔐 OCI Authentication & Authorization

This lesson explores the key concepts of **Authentication (AuthN)** and **Authorization (AuthZ)** in Oracle Cloud Infrastructure (OCI), along with related entities like **principals**, **groups**, and **IAM policies**.

---

## 👤 What is a Principal?

A **principal** is an IAM entity that can interact with OCI resources. There are two types:

- **Users**: Human users accessing OCI via Console, CLI, or SDK.
- **Resource Principals**: OCI resources (e.g., compute instances) that can **act as principals** to make API calls.

> 🔸 *Groups* are collections of users with the same access needs.

---

## 🔑 Authentication (AuthN)

Authentication confirms **who you are**. In OCI, there are **three main methods**:

### 1. **Username & Password**
- Standard login method for console access.

### 2. **API Signing Keys**
- Used with CLI or SDK.
- Based on an **RSA key pair** (public and private keys).
- Signs API requests for secure communication.

### 3. **Authentication Tokens**
- Oracle-generated strings for services that **don’t support OCI's standard auth model**.
- Example use case: Authenticating Autonomous Data Warehouse API calls.

---

## ✅ Authorization (AuthZ)

Authorization determines **what actions a principal can perform**. In OCI, it's managed through **IAM policies**.

### 🔓 IAM Policies

Policies are **human-readable** statements that define access permissions.

### 🔤 Syntax:
Allow group <group_name> to <verb> <resource-type> in <location>


- **group**: Target group (policies can’t be written for individual users)
- **verb**: Type of access (`manage`, `use`, `read`, `inspect`)
- **resource-type**: Type of OCI resource (e.g., `instances`, `volumes`)
- **location**: `tenancy` or a specific `compartment`

> All access is **denied by default** — only explicitly allowed actions are permitted.

---

### 🔁 Policy Verbs Breakdown

| Verb     | Description                                          |
|----------|------------------------------------------------------|
| `manage` | Full control (includes all below)                    |
| `use`    | Read & create, but no updates or deletes             |
| `read`   | View resources only                                  |
| `inspect`| Limited metadata visibility (minimal read access)    |

### 🎯 Granularity

- Policies can target **all resources**, **specific services**, or even **specific resource types** (e.g., only compute instances).
- Can apply to **entire tenancy** or just a **compartment**.

---

## 🧾 Summary

| Concept          | Description                                                  |
|------------------|--------------------------------------------------------------|
| Principal         | User or OCI resource that interacts with OCI                |
| Authentication    | Confirms identity using password, API keys, or auth tokens  |
| Authorization     | Grants permission using IAM policies                        |
| Policy Syntax     | `Allow group <group> to <verb> <resource> in <location>`    |
| Access Scope      | Can be scoped to tenancy or compartment                     |
| Policy Verbs      | `manage`, `use`, `read`, `inspect`                          |

OCI’s **IAM system** allows for powerful, secure, and fine-grained access control using **principals**, **authentication mechanisms**, and **human-readable policies**.

---

*Next: We'll explore dynamic groups and conditions for more advanced access control.*
