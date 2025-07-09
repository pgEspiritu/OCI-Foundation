# 📁 OCI File Storage Service Overview

---

## 📌 What Is File Storage?

- **File storage** is a **hierarchical collection of documents** organized into named directories.
- Commonly used in both **Linux (NFS)** and **Windows (SMB)** systems.
- In the cloud, file storage is **distributed** and not local to your machine.

---

## 🔄 Supported Protocols

- **NFS (Network File System)** – used in Linux/Unix systems.
- **SMB (Server Message Block)** – used in Windows environments.
- Both protocols are widely supported by modern **operating systems and hypervisors**.

---

## 💼 Use Cases for OCI File Storage

- **Enterprise Applications**: e.g., Oracle E-Business Suite (EBS) requires shared file storage.
- **General Purpose File Systems**: Corporate shared directories and folders.
- **Microservices & Containers**: Maintain **state** using shared file systems (typically stateless by nature).
- **High Performance Computing (HPC)**, **Scale-Out Apps**, **Analytics**, and more.

---

## 🧱 How It Works

- Multiple **compute instances** in a data center can **share a single file system**.
- Compute instances **read/write** to the shared storage.

```text
[ Compute Instances ]
↓
[ OCI File Storage Service (Shared File System) ]
```


---

## 🔒 Security & Backups

- **Encryption at REST**: All stored data is encrypted.
- **Encryption in Transit**: Traffic between compute instances and file system is encrypted.
- **Snapshots**: Used for backup and data protection (e.g., recovery from deletions).

---

## 🚀 Getting Started (Basics)

> *This foundational overview does not cover setup steps in detail.*

- Create a **file system** in OCI.
- **Mount** it to one or more compute instances.
- Start reading/writing files as you would on a local directory.

---

## 📝 Summary

OCI File Storage Service offers **shared, secure, and distributed file storage** ideal for:
- Enterprise applications
- Shared directories
- Stateless containers needing persistent state
- Analytics and HPC workloads
