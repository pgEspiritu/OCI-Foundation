# 🔐 OCI Vault Service

The **OCI Vault** is a managed service for centrally managing **encryption keys** and **secret credentials**. It eliminates the need to store sensitive data like keys and credentials in config files or code, thereby enhancing security.

---

## 🔑 What Are Keys and Secrets?

- **Key**: Specifies how plaintext is transformed into ciphertext (and vice versa).
- **Secret**: Credentials such as:
  - Passwords
  - Certificates
  - SSH Keys
  - Authentication Tokens

> Vault allows central management of these components, reducing the risk of exposing them in code or config files.

---

## 🧰 Key Protection Modes

| Mode     | Description                                                                 |
|----------|-----------------------------------------------------------------------------|
| Software | Keys are stored on a server and can be exported                            |
| HSM      | Keys are stored in a Hardware Security Module; **cannot be exported**       |

- OCI uses **FIPS 140-2 Level 3 certified** HSMs.
- Cryptographic operations for HSM-protected keys are performed **within the HSM**.

---

## 🧪 Supported Algorithms

- **AES** (Symmetric): Same key used to encrypt and decrypt.
- **RSA** (Asymmetric): Public key encrypts, private key decrypts.
- **ECDSA**: Used for digital signatures, **not** for encryption/decryption.

---

## 🔄 Key Rotation & Integration

- Keys can be rotated without re-encrypting all data.
- Keys are integrated with other **OCI services** (e.g., Object Storage, Block Volume).
- Vault is a **regional service** and provides **public API endpoints**.

---

## 🔐 Envelope Encryption

A **two-tiered** encryption strategy:

1. **Data Encryption Key (DEK)**: Used to encrypt actual data.
2. **Master Encryption Key (MEK)**: Used to encrypt the DEK.

```text
Plaintext Data → Encrypted using DEK
DEK → Encrypted using MEK stored in Vault
```

---

### 🔐 Master Encryption Key (MEK) Management

- Access to MEKs is managed via **IAM policies**.
- **Audit logs** track all key-related activities.
- **MEK rotation** does **not** require data re-encryption.
- ⚠️ **If the master key is deleted, all associated data becomes unrecoverable.**

---

### 🗑️ Vault Deletion & Retention

- **Vault deletion is not immediate.**
- You can configure a **waiting period (7–30 days)**.
- Once deleted, the **Vault and all its keys are permanently removed**.
- **Data encrypted with deleted keys is irretrievable.**

---

### 🧪 Example: Object Storage Encryption Process

#### 🔐 Encryption Flow

1. Plaintext is uploaded to **Object Storage**.
2. Object Storage calls **Vault** to:
   - Generate a **data key (DEK)**
   - Encrypt the DEK using the **master key (MEK)**
3. Data is encrypted using the **plaintext DEK**
4. Both the **encrypted object** and **encrypted DEK** are stored in the bucket

#### 🔓 Decryption Flow

1. Encrypted object and encrypted DEK are retrieved
2. **Vault** uses the MEK to decrypt the DEK
3. DEK is used to decrypt the object and return **plaintext**

---

### ✅ Recap

**OCI Vault** helps you securely manage:

- 🔑 **Encryption keys**
- 🔐 **Secrets** like passwords, SSH keys, tokens

Supports:
- ✅ **AES** (symmetric encryption)
- ✅ **RSA** (asymmetric encryption)
- ✅ **ECDSA** (digital signing only)

Key Features:
- 🔁 Uses **Envelope Encryption** (MEK + DEK)
- 🔄 Integrated with multiple **OCI services**
- 🔐 Enforces **key lifecycle policies**
- 🚫 Limits **blast radius** via layered key management
