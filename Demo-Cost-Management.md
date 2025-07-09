# 💰 OCI Cost Management Demo

Welcome to this demo on **OCI Cost Management tools**. This walkthrough shows how to access, analyze, and control your cloud spend using the OCI Console.

---

## 🧭 Navigation

1. Go to the **Navigation Menu**
2. Select **Billing and Cost Management**

You'll see a set of tools:
- **Cost Analysis**
- **Cost and Usage Reports**
- **Budgets**

---

## 📊 Cost Analysis

### Features:
- Visualize and track spending by:
  - Service (e.g., Compute, Database)
  - Region (e.g., Ashburn, Phoenix)
  - Compartment
  - Tags (e.g., CreatedBy)
- Adjust filters to view:
  - Daily/monthly costs
  - Historical trends (e.g., Jan–May 2023)

### Example Usage:
- Total monthly spend: `$23`
- Most costs from `Compute` & `Database`
- Compartment breakdown shows:
  - `Networking` → $21 of $23
- Region breakdown:
  - Phoenix → $15
  - Ashburn → $7

### Tag-Based View:
- View costs by **user** or **creator**
- Example: `Sergio` created compute instances consuming most cost
- Save views as custom reports:
  - e.g., **"Tag-Based Report"**

---

## 📈 Budgets

### Purpose:
- Track and control spend per **compartment** or **cost-tracking tags**

### Steps:
1. Go to **Budgets**
2. Click **Create Budget**
3. Set parameters:
   - Name (e.g., `Sandbox Budget`)
   - Compartment
   - Start Date
   - Monthly Amount (e.g., `$100`)
4. Configure **Alert Rule**:
   - Trigger at `%` threshold (e.g., 90%) or specific amount
   - Provide email to receive alerts

### Outcome:
- When usage hits $90 (90%), an email notification is sent
- Helps monitor spend and take corrective action

---

## ✅ Summary

OCI Cost Management provides:

- **Cost Analysis** – Visual reports with filters by time, service, compartment, tags, etc.
- **Budgets** – Track and alert on usage per compartment or tag
- **Usage Reports** – CSV-based reports for auditing and reconciliation
- **Cost Reports** – Invoice-level detail at the resource level

> Use these tools to stay informed and in control of your OCI spend.

---
