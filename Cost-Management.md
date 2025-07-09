# 💸 OCI Cost Management

Welcome to this lesson on **Cost Management** in Oracle Cloud Infrastructure (OCI). In this session, we’ll explore the tools OCI provides to help monitor, analyze, and control your cloud spending.

---

## 📊 OCI Budgets

- Create **budgets** for a specific **compartment** to monitor and control spending.
- Set up **alerts** to notify you when:
  - Spending exceeds a defined threshold.
  - Forecasted spend is expected to exceed your budget.

### ✅ Example:
- Budget 1: `$1,000`
- Budget 2: `$100`
- Alerts help ensure you stay within your cost plan.

---

## 📈 Cost Analysis

- **Analyze past spending** to understand trends.
- Useful for optimizing and adjusting future cloud usage.
- Visual breakdowns by service, compartment, or tags.

---

## 📄 Usage Reports

- Daily **CSV files** show detailed usage for each resource in your tenancy.
- Stored in an **Object Storage bucket**.
- Can be accessed across **multiple tenancies** via **cross-tenancy policies**.

---

## 🚦 Service Limits & Quotas

### Service Limits:
- Each OCI service has **default limits** to avoid misuse.
- View and request **increases** when needed (e.g., more CPUs, VMs).

### Quotas:
- Set **maximum allowed resources** in a compartment.
- Examples:
  - Limit to 10 VMs in `Dev` compartment.
  - Set **Exadata usage to 0** in a non-production compartment.

---

## 🧱 Compartments for Cost Isolation

- Use compartments to:
  - Isolate usage by team, department, or project.
  - Apply specific quotas or budgets.
  - Improve cost tracking and governance.

---

## ✅ Recap

OCI provides several tools to help manage and control costs:

- 🧮 **Budgets** – Track forecasted vs. actual spending.
- 📊 **Cost Analysis** – Understand past costs and trends.
- 📄 **Usage Reports** – Daily logs of all resource usage.
- 🚦 **Service Limits** – View and request capacity increases.
- 📉 **Quotas** – Limit resource usage per compartment.
- 🧱 **Compartments** – Logical isolation for better cost control.

📘 **Tip:** Refer to OCI documentation for deeper guidance on each feature.

---

