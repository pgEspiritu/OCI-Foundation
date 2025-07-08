# ☁️ OCI Object Storage – Quick Demo Guide

This demo walks through how to **create a bucket**, **upload an object**, and **manage access** in Oracle Cloud Infrastructure (OCI) Object Storage.

---

## 🧭 Steps Overview

### 1. Navigate to Object Storage
- Log in to the **OCI Console**
- Go to **Navigation Menu** → **Storage** → **Object Storage**

---

### 2. 🪣 Create a Bucket
- Click **Create Bucket**
- Set:
  - **Name** (or accept the default)
  - **Storage Tier**: 
    - `Standard`, `Infrequent Access`, or `Archive`
  - (Optional) Enable **Auto-Tiering**
  - Choose **Encryption**:
    - Oracle-managed (default)
    - Bring Your Own Key (BYOK) using OCI Vault
- Click **Create**

📌 *Note: Storage tier cannot be changed after creation.*

---

### 3. 📤 Upload an Object
- Inside the bucket, click **Upload**
- Choose and upload a file from your local machine
- After upload:
  - View file size
  - Access **Object Details**
  - Copy **Public URL**

---

### 4. 🔒 Access Control

#### 🔐 By Default: Private Bucket
- Accessing the object via its public URL gives an **error**:
  - “Bucket not found” or “unauthorized”

#### 🌐 Option A: Make Bucket Public (Not Recommended)
- Edit bucket visibility to **Public**
- Anyone with the URL can access the object
- ⚠️ **Warning**: OCI recommends *not* making buckets public

#### 🔐 Option B: Use Pre-Authenticated Request (Recommended)
- Keep bucket **Private**
- Go to object → More Options (...) → **Create Pre-Authenticated Request**
  - Choose **Object** scope
  - Define **access level** and **expiration date**
- Copy the generated **URL with security token**
  - Accessible **only** by users with the full URL

✳️ **Example Difference**:

| Type                   | Access                      |
|------------------------|-----------------------------|
| Regular Public URL     | ❌ Access denied if private  |
| Pre-Auth URL           | ✅ Access with token in URL  |

---

## 🧠 Key Takeaways

- **Object Storage** allows simple web-based access to files.
- **Bucket visibility** controls access:
  - Public: open to everyone
  - Private: access controlled via policies or **pre-authenticated requests**
- **Pre-authenticated URLs** are secure and time-limited, best for sharing objects privately.
- **Auto-tiering** and **encryption** settings are available during bucket creation.
