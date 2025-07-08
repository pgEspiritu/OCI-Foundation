# ☁️ OCI Object Storage

OCI Object Storage is an **internet-scale**, **high-performance**, and **fully managed** object-based storage platform ideal for storing **unstructured data**.

---

## 🔍 Key Characteristics

- Stores data as **objects** (key-value pairs)
- Ideal for: 📷 Images, 🎥 Videos, 📄 Logs, 📁 Backups
- Accessed via public API (HTTP/HTTPS)
- **Regional** and **highly durable**
- Offers **private access** from OCI resources like compute instances
- Feature-rich (lifecycle, versioning, auto-tiering, encryption)

---

## 📦 Object Storage Core Components

| Component     | Description                                                                 |
|---------------|-----------------------------------------------------------------------------|
| **Object**     | The actual data, stored with metadata                                       |
| **Bucket**     | Logical container for grouping objects (unique within a tenancy)           |
| **Namespace**  | Top-level logical grouping for all buckets and objects (globally unique)   |
| **Flat Hierarchy** | No actual folders — structure simulated using **prefixes**             |

---

## 🌐 Example API Path Structure

`https://objectstorage.<region>.oraclecloud.com/n/<namespace>/b/<bucket-name>/o/<object-name>`

```makefile
Example: https://objectstorage.us-sanjose-1.oraclecloud.com/n/myacct/b/development/o/log.zip
```

---

## 🗃️ Storage Tiers

| Tier                     | Description                                | Min Retention | Access Speed                        | Cost           |
|--------------------------|--------------------------------------------|----------------|-------------------------------------|----------------|
| **Standard (Hot)**       | Frequently accessed critical data          | None           | ⚡ Instant                          | 💰 Highest     |
| **Infrequent Access (IA)** | Long-term storage (e.g., backups)       | 31 days        | ⚡ Instant                          | 💸 60% cheaper |
| **Archive**              | Rarely accessed data (like tape backups)   | 90 days        | 🕐 ≥ 1 hour (restore + download)    | 💸 Cheapest    |

---

## ⚙️ 🔁 Auto-Tiering

- Automatically shifts objects between **Standard** and **Infrequent Access** tiers.
- Based on access patterns.
- ⚠️ No retrieval fees or pro-rated storage penalties.
- ✅ Ideal for unknown or dynamic access behavior.

---

## 🔄 Lifecycle Management

- Automates object transition and deletion using **rules**.
- Example policy:
  - Move to **Archive** after 30 days.
  - **Delete** after 180 days.

```json
{
  "action": "Archive",
  "daysSinceLastModification": 30
}
```

---

## 🧬 Versioning

- Enable versioning at the **bucket level**.
- Automatically maintains **history of changes** to stored objects.

---

## 🔐 Data Encryption

| Option              | Description                                 |
|---------------------|---------------------------------------------|
| **Default Encryption** | Always enabled (no configuration needed) |
| **BYOK**               | Bring Your Own Key for enhanced security |

---

## 🛠️ Access Methods

Access Object Storage using:

- **REST API** with familiar HTTP verbs:
  - `PUT` – Upload
  - `GET` – Download
  - `DELETE` – Remove
- **OCI Console**
- **OCI CLI**
- **OCI SDKs**
- **Pre-Authenticated Requests**
- **IAM Policies**
- **OCI Vault**

---

## 🎯 Use Cases

✅ Media backup and streaming  
✅ Logs and telemetry storage  
✅ Big Data lakes  
✅ Static website hosting  
✅ Disaster recovery and archival  

---

## 🧠 Summary

| Feature                | Supported                                 |
|------------------------|--------------------------------------------|
| **Public access**      | ✅ Yes (via URL or API)                     |
| **Private compute access** | ✅ Yes (via VCN or IAM policies)       |
| **Lifecycle policies** | ✅ Yes                                      |
| **Versioning**         | ✅ Yes                                      |
| **Auto-tiering**       | ✅ Yes                                      |
| **Encryption**         | ✅ Always enabled                          |
| **Restore from archive** | ⏱️ ~1 hour (plus download window)      |

---

📸 **Next time you upload a photo or stream a video, it may be stored in OCI Object Storage!**

