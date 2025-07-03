# 🏗️ OCI Tenancy Setup – Best Practices

This lesson outlines how to set up your Oracle Cloud Infrastructure (OCI) tenancy following best practices for secure and efficient management.

---

## ✅ Best Practices for Tenancy Setup

### 1. **Avoid Using Tenancy Administrator for Day-to-Day Ops**
- The tenancy administrator (creator of the OCI account) should not perform regular operational tasks.
- Instead, assign a dedicated **OCI Admin Group** for daily operations.

### 2. **Use Dedicated Compartments for Resource Isolation**
- Organize resources into separate compartments such as:
  - `sandbox`, `dev`, `prod`
  - Business unit-specific compartments
  - Region-based compartments (e.g., `NA`, `EU`)
- Avoid placing all resources under the **Root Compartment**.

### 3. **Enforce Multi-Factor Authentication (MFA)**
- Strengthens login security by requiring:
  - **Something you know** (password)
  - **Something you have** (device/token)
- Enforce MFA for all users, especially administrators.

---

## 🔐 Recommended Policies for OCI Admins

To enable OCI Admins to manage resources (like a tenancy admin), you need to assign the following IAM policies:

### 🛠️ General Resource Access
```hcl
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE all-resources IN tenancy
```

## 🔐 IAM Resource Permissions (granular)
These policies should be added to allow management of identity-related resources:

```hcl
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE domains IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE users IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE groups IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE dynamic-groups IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE policies IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE compartments IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE tag-namespaces IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE tag-defaults IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE identity-providers IN tenancy
ALLOW group <sandbox_domain>/<OCI_Admin_Group> TO MANAGE network-sources IN tenancy
```

> ℹ️ You may scope these to specific compartments instead of the tenancy if preferred:

```hcl
IN compartment <compartment_name>
```

---

## 📌 Summary

| **Aspect**             | **Recommendation**                                                                 |
|------------------------|-------------------------------------------------------------------------------------|
| **Admin Access**       | Use a dedicated **OCI Admin Group**                                                |
| **Resource Management**| Isolate resources using **compartments**                                           |
| **Authentication**     | Enforce **Multi-Factor Authentication (MFA)** for all users                        |
| **Policy Configuration** | Grant **fine-grained access** using identity-specific resource types               |

---

## 💡 Key Takeaways

- 🔐 Follow the **principle of least privilege** by scoping policies appropriately.  
- 📦 Use **compartmentalization** to mirror your organizational or functional structure.  
- 🚫 Never use the **tenancy administrator** for regular operations.  
- 🔍 Regularly **audit IAM policies and group memberships** to maintain a secure environment.
