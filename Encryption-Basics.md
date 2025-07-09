# 🔐 Encryption Basics in OCI

This lesson covers the fundamentals of encryption, types of encryption, common algorithms, and an introduction to Hardware Security Modules (HSMs).

---

## 📘 What Is Encryption?

- **Encryption** transforms **plaintext** into **ciphertext** — a randomized series of letters/numbers that is unreadable without a key.
- **Decryption** is the reverse process: transforming ciphertext back into readable plaintext.
- **Key**: A string (numbers/letters) used to encrypt or decrypt data via a cryptographic algorithm.

---

## 🔑 Keys & Key Pairs

- A **key** or **key pair** is generated for a specific algorithm and can be used for:
  - Encryption/Decryption
  - Digital signing

### 🔁 Encryption Process

```text
Plaintext + Key (with algorithm) → Ciphertext
Ciphertext + Key (with algorithm) → Plaintext
```

---

## 🗄️ Encryption at Rest vs In Transit

### 🔒 Encryption at Rest
- Data stored on physical devices (e.g., databases, file systems)
- Unreadable without the decryption key
- Protects against data theft if a device is compromised

### 🌐 Encryption in Transit
- Data moving between systems (e.g., client ↔ server)
- Example: HTTPS protocol
- Protects data during network transmission

---

## 🔁 Symmetric Encryption

- Same key used for encryption and decryption
- Fast and efficient

**Example use-case:**
- John encrypts a message with a secret key
- Mike decrypts the message using the same key

> ❗ **Drawback**: Sharing the same key securely is a challenge

---

## 🔁 Asymmetric Encryption

- Two keys: **Public key** & **Private key**
- Public key → used for encryption (can be shared)
- Private key → used for decryption (kept secret)

**Example Workflow:**
- Mike generates a public/private key pair
- John encrypts a message using Mike’s public key
- Only Mike can decrypt it using his private key

> ✅ **Advantage**: Secure even if public key is widely shared

---

## 🔢 Common Encryption Algorithms

| Algorithm | Type                | Description                                                                 |
|----------:|---------------------|-----------------------------------------------------------------------------|
| **AES**   | Symmetric           | Advanced Encryption Standard; uses 128-, 192-, or 256-bit keys              |
| **RSA**   | Asymmetric          | Public key encrypts, private key decrypts; slower but secure                |
| **ECDSA** | Asymmetric (Signing)| Elliptic Curve Digital Signature Algorithm; used for digital signatures only|

---

## 🧱 Hardware Security Module (HSM)

A physical device that:
- Manages and safeguards cryptographic keys
- Performs encryption/decryption functions
- Ensures strong authentication and tamper detection

### 🔐 Key Features
- Tamper-evident and tamper-resistant
- Meets standards like:
  - **FIPS 140-2 Level 3**
  - **Common Criteria**
- Automatically deletes keys if tampered with

### ✅ In OCI
- OCI's **Vault** service uses HSMs for key management
- HSMs meet **FIPS 140-2 Level 3** certification

---

## ✅ Summary

- **Encryption** protects data confidentiality
- Two main types:
  - **Symmetric** (one key)
  - **Asymmetric** (key pair)
- Common algorithms:
  - **AES** for symmetric encryption
  - **RSA** for asymmetric encryption
  - **ECDSA** for digital signatures
- Understand **Encryption at Rest** vs **Encryption in Transit**
- **HSMs** provide secure key management with hardware-level assurance
