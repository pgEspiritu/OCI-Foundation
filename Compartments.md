# 🧩 OCI Compartments Overview

This lesson provides an overview of **Oracle Cloud Infrastructure (OCI) Compartments**, a unique and powerful feature used to organize and control access to cloud resources.

---

## 📦 What is a Compartment?

- A **compartment** is a **logical container** for organizing and isolating cloud resources.
- When an OCI tenancy (account) is created, a **Root Compartment** is provided by default.
- **Best practice**: Create dedicated compartments for different resources (e.g., network, storage, compute) rather than using the Root Compartment for everything.

---

## 🧭 Why Use Compartments?

### ✅ Key Benefits:
- **Isolation**: Group related resources logically (e.g., storage in a storage compartment).
- **Access Control**: Apply **fine-grained policies** to control who can access what within each compartment.
- **Organization**: Mirrors organizational or project structures, making resource management more intuitive.
- **Cost & Quota Control**: Set **budgets** and **quotas** at the compartment level.

---

## 🔄 Resource Management in Compartments

- A **resource belongs to one compartment** only.
- Resources **can interact** across compartments.
  - Example: A compute instance in Compartment A can use a VCN in Compartment B.
- Resources **can be moved** between compartments (with some limitations).

---

## 🌍 Global Nature of Compartments

- Compartments are **global constructs**:
  - Visible and usable across all OCI regions within the tenancy.
- Policies can still be written to restrict **region-specific access**.
- Compartments support **nesting up to 6 levels**, allowing flexible modeling of organizational hierarchies.

---

## 💰 Quotas and Budgets

- OCI allows **setting quotas** (e.g., no bare metal instances in a compartment).
- You can define **budgets** to receive alerts if spending exceeds a set threshold per compartment.

---

## 🧾 Summary

| Feature            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| Root Compartment   | Default container in every tenancy                                          |
| Child Compartments | Custom containers for organizing resources                                  |
| Isolation          | Segregate resources for security and manageability                          |
| Policies           | Control access by writing compartment-scoped policies                       |
| Resource Movement  | Resources can be transferred across compartments                            |
| Global Scope       | Compartments are accessible across regions                                  |
| Nesting            | Up to 6 levels deep; supports organizational modeling                       |
| Quotas/Budgets     | Control resource usage and cost per compartment                             |

---

**OCI Compartments** are essential for building secure, scalable, and manageable cloud environments. Proper compartment design aligns your cloud infrastructure with your organizational structure and governance requirements.

*Thanks for reading!*
