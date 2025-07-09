# 🛡️ OCI Security Zones Demo

This demo shows how to create a **Security Zone**, enable **Cloud Guard**, and enforce security policies in OCI.

---

## 🔐 What Are Security Zones?

- A **Security Zone** is a compartment where **security policies cannot be violated**.
- When creating a security zone, you:
  - Select **compartments**
  - Choose a **Security Zone Recipe** (Oracle-managed or custom)
- OCI **denies any operation** that violates these policies.
- Security Zones rely on **Cloud Guard** to scan and report policy violations.

---

## ⚙️ Prerequisite: Enable Cloud Guard

1. Go to **Identity & Security → Security Zones**.
2. OCI shows a **workflow** with required steps.
3. If Cloud Guard is not enabled:
   - Click **Enable Cloud Guard**
   - Grant necessary **IAM policies** (OCI lists them)
   - Choose a **Reporting Region** (e.g., `Ashburn`)
   - Choose whether to monitor **All Compartments** or specific ones
   - Set **Detector Recipes**
   - Click **Enable**

✅ Once enabled, Cloud Guard will begin monitoring your tenancy.

---

## 🛠️ Create a Security Zone

1. Navigate to **Security Zones → Overview**
2. Click **Create Security Zone**
3. Choose a recipe:
   - `Oracle-managed` (default) or
   - `Customer-managed`
4. Name the zone (e.g., `sandbox-sec-zone`)
5. Assign it to a **compartment** (e.g., `sandbox`)
6. Click **Create Security Zone**

⏱️ In a few seconds, the security zone is ready and policies are enforced.

---

## 📜 Security Policies Example

Clicking on the zone will show enforced policies, such as:

- **Compute**: Disallow public IPs
- **Storage**: Buckets must use **Customer Managed Keys**
- **Networking**: Subnets must be private
- **Database**: Enforce encryption

---

## 🚫 Test a Policy Violation

Let’s create an **Object Storage Bucket** in the security zone:

1. Go to **Storage → Object Storage → Create Bucket**
2. Ensure you're in the `sandbox` compartment (security zone enabled)
3. By default, OCI uses **Oracle-managed keys**
4. But security zone policy requires **customer-managed encryption keys**
5. Since you have no key or vault access:

   - ❌ **Bucket creation is denied**
   - OCI shows:
     - **Error Message**: Security Zone Policy Violation
     - **Reason**: "Encrypt the bucket with a customer-managed key"
     - **Fix**: Workflow to create and use your own encryption key

---

## 🧠 Summary

- **Security Zones** + **Cloud Guard** = Strong security posture
- Violations are **automatically blocked**
- Policies are clearly enforced and user-friendly
- You can only create resources that comply with defined **security recipes**
