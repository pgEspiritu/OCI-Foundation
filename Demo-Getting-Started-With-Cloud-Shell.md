# 🔐 OCI Cloud Shell – SSH Key Generation Demo

## 📌 What is OCI Cloud Shell?
- A **browser-based Linux shell environment** pre-configured with:
  - OCI CLI (pre-authenticated)
  - Utilities like Git, Java, Python, etc.
- Accessible from:  
  **OCI Console → Developer Tools → Cloud Shell**

---

## 🛠️ Steps to Generate SSH Key Pair

### ✅ 1. Access Cloud Shell
From the **OCI Console**, open **Cloud Shell** via the global menu.

### ✅ 2. Create a Directory (Optional)
Organize your SSH keys by creating and navigating to a new directory:
```bash
mkdir ssh-keys-demo
cd ssh-keys-demo
```

### ✅ 3. Generate the SSH Key Pair
Use the following command:
```bash
ssh-keygen -t rsa -b 2048 -f demo_key
```

- `-t rsa`: Specifies the RSA algorithm
- `-b 2048`: Key length of 2048 bits
- `-f demo_key`: Output file name
- Skip passphrase (optional for automation)

---

### Verify Key Files
List the files:
```bash
ls
```

Expected files:
- `demo_key` → Private key
- `demo_key.pub` → Public key

---

# 🔑 SSH Key Concepts

| **Component**     | **Description**                                                             |
|------------------|------------------------------------------------------------------------------|
| **Public Key**    | Copied to the **remote server**                                             |
| **Private Key**   | Remains **securely with the user**                                          |
| **Authentication**| Works if the **private key matches** the public key on the server           |

---

# 💡 Why Use **OCI Cloud Shell** for SSH Keys?

- ✅ No need for tools like **PuTTYgen** or a local terminal setup  
- ✅ Keys are securely **generated and stored** directly in OCI Cloud Shell  
- ✅ Keys can be **easily reused** for Compute instance access in OCI  

---

# 🧠 Recap

You’ve learned how to:

- 🚀 Access **OCI Cloud Shell**
- 🔐 Generate an **RSA SSH key pair**
- 📘 Understand **SSH key usage and purpose**

> 🔒 **Security Reminder:**  
> Only use the **public key** to connect to OCI compute instances.  
> **Keep your private key secure** and never share it.
