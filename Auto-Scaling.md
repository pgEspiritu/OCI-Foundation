# 📈 OCI Compute Scaling

Welcome to this lesson on **Scaling** — a key concept in OCI Compute!

---

## 🔧 What is Scaling?

Scaling refers to adjusting the capacity of your compute resources to meet application demand. There are two main types:

### 1. 🧱 Vertical Scaling (Scale Up/Down)
- **Definition:** Increase or decrease the size (shape) of a VM (more CPU, memory, etc.)
- **Scalable Attributes:** OCPUs, Memory
- **Requires Downtime:** ✅ Yes
- **Best Practice:** Stop your instance before performing vertical scaling

### 2. 📊 Horizontal Scaling (Autoscaling)
- **Definition:** Add or remove VMs of the same shape
- **Advantages:**
  - Handles **traffic spikes** automatically
  - Enables **high availability**
  - ✅ No extra cost
- **Types:**
  - **Scale-Out:** Add more VMs
  - **Scale-In:** Remove VMs

---

## ⚙️ How Autoscaling Works

Autoscaling is based on three simple steps:

### 🔹 Step 1: Create an Instance Configuration
- A "stamp" or **template** of a running instance
- Includes:
  - Image
  - Shape
  - Networking
  - Storage
  - Metadata

### 🔹 Step 2: Create an Instance Pool
- A **group of instances** managed as a single unit
- Benefits:
  - Batch actions (start/stop/terminate)
  - Can be placed across **availability domains**

### 🔹 Step 3: Define Autoscaling Policies
- Set:
  - **Initial Size**
  - **Minimum Size**
  - **Maximum Size**
- Define rules based on metrics:
  ```text
  If CPU > 70% → Add 2 instances
  If CPU < 30% → Remove 1 instance
  ```

  ---

  ## 🔁 Constant Monitoring

OCI continuously monitors:

- **CPU usage**
- **Memory usage**
- **Traffic metrics**

Based on these metrics, it **automatically triggers scaling actions** according to your configured rules.

---

## 🧠 Recap

| Type                          | Description                                | Downtime | Use Case                                  |
|------------------------------|--------------------------------------------|----------|-------------------------------------------|
| **Vertical Scaling**         | Change instance shape (CPU, RAM)           | ✅ Yes   | Performance tuning                        |
| **Horizontal Scaling (Autoscaling)** | Add/remove VMs automatically             | ❌ No    | Traffic demand & high availability        |
