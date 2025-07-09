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

| **Performance Tier**             | **Max IOPS per GB** | **Max Throughput (MB/s per GB)** | **Use Case**                                              | **Provisioned IOPS Support** |
|----------------------------------|----------------------|-----------------------------------|------------------------------------------------------------|-------------------------------|
| **Lower Cost**                   | 2 IOPS/GB            | 0.5 MB/s/GB                        | Backup, archival, infrequent access                        | ❌ No                         |
| **Balanced**                     | 60 IOPS/GB           | 0.48 MB/s/GB                       | General-purpose workloads, boot volumes                    | ❌ No                         |
| **Higher Performance**           | 75 IOPS/GB           | 0.56 MB/s/GB                       | High-performance databases, latency-sensitive apps         | ❌ No                         |
| **Ultra High Performance (Custom)** | Up to 300 IOPS/GB | Up to 1 MB/s/GB                   | Mission-critical apps, large-scale databases               | ✅ Yes                        |

---

### 🔎 Notes:
- **Ultra High Performance** allows **custom IOPS and throughput provisioning**.
- Performance scales with **volume size**, subject to OCI service limits.
- All volumes are **encrypted at rest** and support **automated backups**.

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
