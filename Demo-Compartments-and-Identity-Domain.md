# 🧪 OCI Demo: Creating Compartments and Identity Domains

This step-by-step demo walks through how to create a **Compartment** and an **Identity Domain** in Oracle Cloud Infrastructure (OCI). 

Compartments are used to **organize and isolate cloud resources**, while Identity Domains serve as containers for **users, groups, and security configurations**.

---

## 📁 Step 1: Create a Compartment

1. **Login** to your OCI Console.
2. Click the **☰ Navigation Menu** > **Identity & Security** > **Compartments**.
3. You will see:
   - A **Root Compartment** (your tenancy)
   - Existing subcompartments (e.g., `development`, `platform-services`)
   - You can nest compartments up to **6 levels deep**.

4. Click **Create Compartment**.
5. Enter the name: `sandbox`.
6. (Optional) Skip the "Security Zone" option for now.
7. Click **Create Compartment**.
8. Refresh the page — you should now see the new `sandbox` compartment listed.

### 🔍 View Compartment Resources

- Navigate to **Governance & Administration** > **Tenancy Management**.
- Use **Tenancy Explorer** to check:
  - Resources under `Root Compartment`
  - No resources under `sandbox` (since it’s just created)

---

## 🔐 Step 2: Create an Identity Domain

1. Go back to the **☰ Navigation Menu** > **Identity & Security** > **Domains**.
2. You’ll see the **default identity domain** listed.
3. Click **Create Domain**.
4. Provide a name: `sandbox-domain`.
5. Choose the **Free SKU** option.
6. (Optional) Skip creating an administrative user.
7. Choose **compartment**:
   - You can choose `Root` or the newly created `sandbox` compartment.
   - For this demo, choose `Root`.
8. Click **Create Domain**.

> 🕒 Wait a few seconds for provisioning.

9. Refresh the page — the `sandbox-domain` should now be listed.

---

## 🔎 Step 3: Review Identity Domain

- Click into `sandbox-domain`.
- You’ll see:
  - **0 Users**
  - **0 Groups**
  - Security settings like **MFA**, **dynamic groups**, etc.

> In the next steps (future demo), you can add users, create groups, and apply security configurations specific to this domain.

---

## ✅ Summary

| Task                | Description                                        |
|---------------------|----------------------------------------------------|
| Compartment         | `sandbox` created under Root                       |
| Identity Domain     | `sandbox-domain` created for user/group isolation  |
| Purpose             | Organize and manage test environments and access   |
| Benefits            | Clean separation of resources and identities       |

OCI’s **compartments** and **identity domains** help maintain **logical separation** and **fine-grained access control** across your cloud tenancy.

---

*Next: We will create users and groups inside the sandbox identity domain.*

Thanks for following along! 🎉
