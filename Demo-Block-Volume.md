# 🚀 OCI Block Volume Service Demo

In this demo, we'll **attach a block volume to a running instance** and then **resize it online** to a larger size. Let's walk through the steps:

---

## 🖥️ Step 1: Access the OCI Console

- Log in to the **OCI Console**.
- Navigate to `Storage` → `Block Storage`.

---

## 🧱 Step 2: Create a Block Volume

- Click **Create Block Volume**.
- Provide a name (e.g., `block-volume-demo`).
- Select the **sandbox compartment** and the appropriate **availability domain** (e.g., `AD-1`).
- Set the size to `100 GB` (custom range: **50 GB to 32 TB**).

---

## ⚙️ Step 3: Configure Performance

OCI provides performance tiers based on **IOPS per GB**:

| Tier                   | IOPS per GB   | Total IOPS (for 100 GB) |
|------------------------|---------------|--------------------------|
| Lower Cost             | 2 IOPS/GB     | 200 IOPS                |
| Balanced               | 60 IOPS/GB    | 6,000 IOPS              |
| Higher Performance     | 75 IOPS/GB    | 7,500 IOPS              |
| Ultra High Performance | 90–225 IOPS/GB| Up to 22,500 IOPS       |

- Max IOPS: **300,000 IOPS** (for larger volumes like 2000 GB).

---

## 🔁 Autotune Options

- **Performance Autotune**: Gradually increases performance in increments (e.g., 10–40 VPUs/GB).
- **Detached Volume Autotune**: Automatically downgrades performance to lower-cost when the volume is detached and restores on reattach.

---

## 🔐 Encryption and Backup

- **Encryption**: Enabled by default (Oracle-managed or customer-managed keys).
- **Other Options**:
  - Backup policy configuration
  - Cross-region replication

Click **Create Block Volume**.

---

## 🔗 Step 4: Attach the Volume to an Instance

- Once created, click on the volume and choose **Attach to Instance**.
- Select:
  - **Attachment Type**: `Paravirtualized` (uses hypervisor)
  - **Access Type**: `Read/Write`
  - **Instance**: Must match the availability domain
  - **Device Path**: Helps maintain consistency after reboot

---

## 🧪 Step 5: Verify Attachment (SSH)

1. SSH into your running compute instance.
2. Run:
   ```bash
   lsblk
   ```
   - You’ll see only the boot volume initially (~46.6 GB).
   - After attaching, refresh and check again to see the new 100 GB block volume.

---

## ⚒️ (Optional) Next Steps
- Partition the Disk
- Format the Disk
- Mount the Disk

> For this demo, we skip these steps. The key takeaway is that the volume is now available and attached.
