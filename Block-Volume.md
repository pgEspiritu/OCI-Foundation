# 📦 OCI Block Volume Service Summary

The **OCI Block Volume** service provides **persistent** and **durable** storage for compute instances.

---

## 🔑 Key Concepts

- **Persistent Storage**: Data persists even after the compute instance is deleted.
- **Durable Storage**: Data is automatically replicated across multiple servers for fault tolerance.

---

## 🧱 How It Works

- Create, attach, detach, and delete volumes.
- Volumes exist independently from compute instances.
- Multiple copies of data ensure durability and availability.

---

## 📊 Block Volume Performance Tiers

| Tier                   | Use Case                                 | IOPS/GiB     |
|------------------------|------------------------------------------|--------------|
| **Lower Cost**         | Large sequential I/O (e.g., streaming)   | ~2 IOPS/GiB  |
| **Balanced**           | Boot disks, general-purpose workloads    | Moderate     |
| **Higher Performance** | I/O-intensive applications               | High         |
| **Ultra High Perf.**   | Databases, highest I/O demand            | Up to 225    |

---

## 🔁 Auto-Tune Performance

- **Feature**: Automatically lowers performance when detached to save costs.
- **Reattaches**: Restores to original performance level.

---

## 🔐 Encryption & Security

- **Encryption at Rest**: Always enabled by default.
- **Encryption in Transit**: Between VM and block storage.
- **Bring Your Own Keys (BYOK)**: Supported for custom security.

---

## 📤 Sharing & Resizing

- **Read/Write Shareable Volumes**: One volume shared by multiple VMs.
- **Online Resizing**: Increase volume size without detaching it.
- **Offline Resizing**: Resize while volume is detached.

---

## 🌍 Replication

- **Cross-region replication** (asynchronous).
- **Use Cases**:
  - Disaster recovery
  - Migration
  - Business expansion

---

## 📦 Volume Groups

- Group multiple block volumes.
- Enable **time-consistent backups** across volumes/instances.
- Restore all grouped volumes from a single backup.
