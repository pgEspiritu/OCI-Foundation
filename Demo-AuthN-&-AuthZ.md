# 🔐 OCI Demo: Authentication and Authorization

This hands-on demo walks through how to implement **Authentication** and **Authorization** in Oracle Cloud Infrastructure (OCI) using **Identity Domains**, **Users**, **Groups**, and **Policies**.

---

## 🧭 Overview

- **Authentication (AuthN)**: Verifies who the user is.
- **Authorization (AuthZ)**: Defines what actions the authenticated user can perform.

---

## 👣 Step-by-Step Instructions

### ✅ Step 1: Access the OCI Console

1. Log in to the **OCI Console**.
2. Go to **☰ Menu > Identity & Security > Domains**.
3. Select the previously created **Sandbox Domain**.

---

### 👤 Step 2: Create a User

1. Click on **Users** under the Sandbox Domain.
2. Click **Create User**.
   - **Name**: `ociadmin`
   - **Email**: (Enter a valid email address)
3. Skip adding the user to a group for now.
4. Click **Create**.

---

### 👥 Step 3: Create a Group

1. Go to **Groups**.
2. Click **Create Group**.
   - **Name**: `OCI Admin group`
3. Add the `ociadmin` user to this group.
4. Click **Create**.

> ✅ **Note**: Policies are assigned to **groups**, not individual users.

---

### 🔓 Step 4: Activate the User (Authentication)

1. Check your email inbox for the **activation email**.
2. Click the link and set a password.
3. After setting the password, log in to the OCI Console using:
   - **Tenancy**: `ocifoundations`
   - **Domain**: `sandbox-domain`
   - **Username**: `ociadmin`
   - **Password**: (your newly created password)

4. You are now **authenticated** but **not yet authorized** to perform actions.

---

### 🚫 Step 5: Confirm Lack of Authorization

Try accessing services like:
- **Compute**
- **Object Storage**

You’ll receive error messages like:

`You are not authorized to perform this request.`

This confirms that **authorization** (permissions) is not yet granted.

---

### 🛡️ Step 6: Grant Authorization with a Policy

1. Switch back to the tenancy admin account.
2. Navigate to **☰ Menu > Identity & Security > Policies**.
3. Click **Create Policy**.

#### Fill in the following:

- **Name**: `oci-admin-policy`
- **Description**: `Policy for object storage access for OCI Admins`
- Use the **Policy Builder**:
  - **Use Case**: Storage Management → Object Storage
  - **Identity Domain**: `sandbox-domain`
  - **Group**: `OCI Admin group`
  - **Compartment**: `sandbox`

✅ Policy Statement Generated:
```text
Allow group sandbox-domain/OCI Admin group to manage buckets in compartment sandbox
Allow group sandbox-domain/OCI Admin group to manage objects in compartment sandbox
```
4. Click Create.

### 🧪 Step 7: Test Access Again as ociadmin
- Go to Object Storage.
- Select Compartment: sandbox.
- Click Create Bucket.
  - Name: Any valid name
- ✅ You should now be able to create a bucket in the sandbox compartment.
> 🚫 Attempting to create a bucket in the Root Compartment will fail due to lack of policy permissions.
- Try accessing Compute: You'll still be unauthorized since no compute policy has been added.

---

## 📌 Summary

| **Element**          | **Description**                                                                 |
|----------------------|---------------------------------------------------------------------------------|
| **Authentication**   | `ociadmin` logs in via the `sandbox` identity domain                           |
| **Authorization**    | Group `OCI Admin group` gets object storage permissions via policy              |
| **Compartment Scoped** | Policy only allows access within the `sandbox` compartment                    |
| **Best Practice**    | Use domain-scoped users & group-based policies for fine-grained access control  |

---

## 🎯 Key Learnings

- **Authentication ≠ Authorization** – Logging in doesn’t mean having permission.
- **Policies are written at the group level** – Always assign permissions to groups, not individuals.
- **Authorization can be scoped** – Apply policies at the **tenancy** or **compartment** level.
- **Policy Builder simplifies policy creation** – Use it to generate accurate policy syntax.
- **Use Identity Domains for isolation** – Helps segregate users, groups, and security configurations.
