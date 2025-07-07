# 🚀 Oracle Container Engine for Kubernetes (OKE)

Welcome to this lesson on **Oracle Container Engine for Kubernetes (OKE)** — a fully managed Kubernetes service on Oracle Cloud Infrastructure (OCI).

---

## 🧱 VMs vs Containers

| Virtual Machines (VMs)                | Containers                          |
|--------------------------------------|-------------------------------------|
| Run on hypervisors (e.g., ESXi)      | Use container runtimes (e.g., Docker) |
| Each VM has its own OS               | Share host OS; no OS inside container |
| Heavier and larger (GBs)             | Lightweight (MBs)                   |
| Slower to boot                       | Fast boot (in seconds)              |
| Higher resource utilization          | Efficient resource usage            |

---

## 🌍 Why Use Containers?

- ✅ **Lightweight** and **fast** to start
- 🔁 **Portable** across environments
- 🧪 Ideal for **DevOps** and **microservices**
- 🛠️ Containers scale easily and consistently

---

## 🔄 What is Container Orchestration?

Container orchestration automates:

- 🔧 Deployment  
- 📡 Networking  
- 📈 Scaling  
- ⚙️ Management

### 🧠 Kubernetes: The Leading Orchestrator

With **Kubernetes**, you get:

- 📈 **Autoscaling** of containerized apps
- 💡 **Self-healing** capabilities
- ✅ **No downtime** deployments
- 🧩 **Simplified deployment** of microservices

---

## 🛠️ What is OKE?

**OKE** = Oracle Container Engine for Kubernetes  
A **fully managed**, **highly available**, and **scalable** Kubernetes service.

### 🔑 Key Features

- One-click cluster creation
- CLI and API support
- Works with **ARM** and **GPU** instances
- Autoscaling support
- Free **control plane**
- Self-healing cluster nodes
- Automatic cluster upgrades

---

## ⚙️ OKE Architecture

```text
+---------------------+      +--------------------------+
|   Control Plane     |      |     Customer Nodes       |
|  (Managed by Oracle)|      |   (Worker Nodes, Pods)   |
+---------------------+      +--------------------------+
```

---

## 🧱 Node
A **physical or virtual machine** with Kubernetes installed.  
Also called a **worker node**.

---

## 🧩 Pod
- Smallest unit of deployment  
- Contains one or more containers sharing:
  - Storage
  - Network resources

---

## 🧠 Control Plane
- **Managed by Oracle**
- Handles:
  - Scheduling
  - Scaling
  - High availability
  - Cluster events

---

## 🔒 etcd
- Key-value store for Kubernetes **cluster state**

---

## 🧰 Cluster Types

| Type      | Description                                | SLA                |
|-----------|--------------------------------------------|--------------------|
| Enhanced  | Full features, autoscaling, SLA-backed     | ✅ Financial SLA    |
| Basic     | Core features, no enhanced functions       | ⚠️ SLO only         |

---

## ☁️ Node Pool Types

| Node Type     | Description                                      | Use in Cluster       |
|---------------|--------------------------------------------------|----------------------|
| Virtual Node  | Serverless, Oracle handles upgrades/patching     | ✅ Enhanced Only      |
| Managed Node  | Customer-managed, flexible, manual upgrades      | ✅ Basic & Enhanced   |

---

## 🧠 Summary

| Feature           | Virtual Node | Managed Node       |
|-------------------|--------------|--------------------|
| Serverless        | ✅ Yes       | ❌ No              |
| Manual upgrades   | ❌ No        | ✅ Yes             |
| Available in      | Enhanced only| Basic & Enhanced   |
| Hands-off mgmt    | ✅ Yes       | ❌ No              |
| Flexibility       | ❌ Limited   | ✅ High            |

---

> **OKE** is ideal for running **cloud-native** and **containerized apps** in a fully managed Kubernetes environment.
