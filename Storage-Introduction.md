# 🗄️ OCI Storage Services Overview

Welcome to this module on **OCI Storage Services**, what they are, and how they work.

---

## 🧠 Key Questions to Determine Storage Needs

Before choosing a storage type, consider:

- 🧍 **Persistence**: Should the storage remain after instance termination?
- 🧾 **Data Type**: Database files, videos, images, logs, etc.
- 🚀 **Performance**: Required IOPS, throughput, latency
- 🔁 **Durability**: How many copies? Replication requirements
- 🔗 **Connectivity**: Local vs. network-attached
- 📡 **Access Protocol**: Block, file, HTTP-based (object)

---

## 🧰 OCI Storage Options

### 1. ⚡ Local NVMe
- **Type**: Locally-attached high-performance SSD
- **Use Case**: High IOPS workloads (e.g. DBs, caching)
- **Characteristics**:
  - Directly attached to compute instance
  - Super low latency
  - Data does **not persist** when instance is terminated

---

### 2. 🧱 Block Volume
- **Type**: Remote, persistent block-level storage
- **Use Case**: Databases, boot volumes, general OS disks
- **Characteristics**:
  - Persistent beyond instance lifetime
  - Accessed as raw block devices (partition > format > mount)

---

### 3. 📁 File Storage
- **Type**: Managed, shared file system
- **Use Case**: Multiple compute instances sharing the same data
- **Characteristics**:
  - NFS protocol support
  - Accessed as files and directories
  - Shared storage across instances

---

### 4. 🗂️ Object Storage
- **Type**: HTTP-accessible object-based storage
- **Use Case**: Web-scale storage for videos, images, logs, backups
- **Characteristics**:
  - Accessed via HTTP (PUT, GET)
  - Ideal for unstructured data
  - Highly durable and scalable

---

## 🚚 Data Migration Services

| Service              | Description |
|----------------------|-------------|
| 📦 Data Transfer Disk     | Ship disks to OCI for data ingestion |
| 🚛 Data Transfer Appliance | Large-capacity devices to bulk-transfer data into OCI |

---

## 🔍 Summary

| Storage Type    | Persistent | Shared | Protocol | Best For |
|-----------------|------------|--------|----------|----------|
| Local NVMe      | ❌ No      | ❌ No   | Block     | High-performance local workloads |
| Block Volume    | ✅ Yes     | ❌ No   | Block     | Databases, OS disks |
| File Storage    | ✅ Yes     | ✅ Yes  | File (NFS)| Shared file systems |
| Object Storage  | ✅ Yes     | ✅ Yes  | HTTP      | Web apps, backups, logs |
