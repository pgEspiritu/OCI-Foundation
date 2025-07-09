## 🔐 OCI Vault Service Demo Summary

### 📍 Accessing the Vault Service
- Navigate to: **OCI Console → Identity & Security → Vault**
- Vault is part of the **OCI Security Services** portfolio.

---

### 🏗️ Creating a Vault
1. Click **Create Vault**
2. Provide:
   - **Vault name** (e.g., `Vault Demo`)
   - **Compartment** (e.g., `sandbox`)
3. Vault Type:
   - ✅ Default (software-protected, free)
   - 🔒 Optional: **Virtual Private Vault** (uses dedicated HSM, incurs cost)
4. Click **Create Vault**

---

### 🔑 Creating a Master Encryption Key (MEK)
1. Inside your vault, click **Create Key**
2. Provide:
   - **Key name** (e.g., `Master Encryption Key`)
   - **Compartment** (same as vault)
3. Protection Mode: Select **Software**
4. Algorithm options:
   - AES (symmetric)
   - RSA (asymmetric)
   - ECDSA (digital signing)
5. Click **Create Key**

✅ Key is now **enabled** and available for use.

---

### 🛡️ IAM Policy: Allow Object Storage to Use the Key

Before using the key in Object Storage:
1. Go to **Policies → Create Policy**
2. Example name: `object-storage-vault-policy`
3. Use the **manual editor** with this statement:
   ```hcl
   allow service objectstorage-us-ashburn-1 to use keys in compartment sandbox
   ```
> 📝 This gives Object Storage permission to use the Vault key.

---

## 🗂️ Creating a Bucket Using Vault Key

1. Go to **Object Storage → Create Bucket**
2. **Select:**
   - **Compartment**: `sandbox`
   - **Encryption Type**: `Customer-Managed Keys`
3. **Choose:**
   - **Vault**: `Vault Demo`
   - **Key**: `Master Encryption Key`
4. Click **Create**

✅ Bucket is now encrypted using your own key from OCI Vault.

---

## ✅ Recap

- **OCI Vault** allows secure, centralized **key and secret management**
- Vault keys can be integrated with OCI services such as:
  - Object Storage
  - Block Volume
  - File Storage
- Using **customer-managed keys** enables:
  - Tighter control over data encryption
  - Compliance with regulatory requirements
- Requires proper **IAM policy** to allow services access to Vault keys
- Supports:
  - **AES** (symmetric)
  - **RSA** (asymmetric)
  - **ECDSA** (digital signing only)
- Key protection modes:
  - 🧠 **Software-based keys** (default, free)
  - 🔐 **HSM-based keys** (more secure, paid)
