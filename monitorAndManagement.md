---

# 🧾 **Azure Monitoring & Management – AZ-900 Cheat Sheet**

---

## ✅ **1. Azure Monitor**

### 📈 What is it?

A **centralized platform** for collecting, analyzing, and acting on telemetry (performance, diagnostics, logs, metrics) from your Azure resources.

---

### 🔍 Key Components:

| Feature        | Purpose                                                             |
| -------------- | ------------------------------------------------------------------- |
| **Metrics**    | Numeric values collected at regular intervals (e.g., CPU % on a VM) |
| **Logs**       | Event data (e.g., activity logs, diagnostics logs)                  |
| **Alerts**     | Triggered based on conditions in metrics or logs                    |
| **Dashboards** | Visualize data in charts/graphs                                     |
| **Workbooks**  | Customizable visual reports                                         |

📌 **Azure Monitor is the umbrella tool** that connects to many services including VMs, containers, apps, databases, and custom apps.

---

### ✅ Use Azure Monitor to:

* View performance data
* Create dashboards
* Set up alerts for metrics/log events
* Route logs to other services (like Event Hub or Storage)

---

## 🔍 **2. Azure Activity Log vs Diagnostic Logs**

| Log Type            | Description                                                           |
| ------------------- | --------------------------------------------------------------------- |
| **Activity Logs**   | Records **control-plane operations** (e.g., who created a VM)         |
| **Diagnostic Logs** | Records **data-plane events** (e.g., read/write to a storage account) |

📌 **Activity Logs = who did what in Azure**
📌 **Diagnostic Logs = how the service behaved**

---

## 🔎 **3. Azure Log Analytics**

### 🔬 What is it?

A **query engine** for analyzing log data collected by Azure Monitor.

* Uses a powerful language: **Kusto Query Language (KQL)**
* Central to investigating problems, trends, and usage

📌 Example use: Find all VMs with CPU usage over 80% in the past hour

💡 Log Analytics is part of **Azure Monitor**, and it's where you write advanced queries for troubleshooting and reporting.

---

## 🚨 **4. Azure Alerts**

* Triggered based on thresholds or patterns in metrics/logs.
* Can **notify via email, SMS, or trigger automation** (Logic Apps, webhooks).
* Use to detect:

  * High CPU usage
  * App errors
  * Unauthorized access attempts

📌 AZ-900 Tip: Alerts are **proactive notifications** that help you respond quickly.

---

## 🧠 **5. Azure Service Health**

### 🩺 What is it?

Tells you about **issues that affect Azure services** **in real time**, including:

* Outages
* Planned maintenance
* Health advisories

---

### Types of Notifications:

| Type                    | Description                                                |
| ----------------------- | ---------------------------------------------------------- |
| **Service Issues**      | Ongoing problems with Azure services                       |
| **Planned Maintenance** | Notifications for upcoming updates                         |
| **Health Advisories**   | Information about changes, recommendations, or retirements |

📌 **Service Health is personalized to your Azure region and services.**

---

## 🔁 **6. Azure Resource Health vs Service Health**

| Tool                | Purpose                                                    |
| ------------------- | ---------------------------------------------------------- |
| **Service Health**  | Health of Azure services across the platform               |
| **Resource Health** | Health of **your specific resources** (e.g., a VM, SQL DB) |

📌 **Service Health** = platform-wide
📌 **Resource Health** = specific resource status (e.g., VM unavailable due to host failure)

---

## ⚙️ **7. Azure Automation**

* Used to **automate repetitive tasks** in Azure (e.g., stop/start VMs, apply patches).
* Supports:

  * **Runbooks** (PowerShell or Python scripts)
  * **Update Management** (schedule patches)
  * **Inventory collection** (track what's installed)

📌 Helps reduce manual effort and enforce operational consistency.

---

## 🧠 Final Exam Tips – Monitoring & Management

| Scenario                                     | Tool                                   |
| -------------------------------------------- | -------------------------------------- |
| Monitor metrics (CPU, memory)                | **Azure Monitor**                      |
| Investigate performance issues using queries | **Log Analytics**                      |
| Notify team if a VM CPU > 90%                | **Alerts**                             |
| Get notified of Azure service outage         | **Service Health**                     |
| Know if your VM is down                      | **Resource Health**                    |
| Automate daily stop/start of VMs             | **Azure Automation**                   |
| Collect update compliance data               | **Update Management (via Automation)** |

---

## ✅ Summary Table – Monitoring & Management Tools

| Tool                      | Purpose                              |
| ------------------------- | ------------------------------------ |
| **Azure Monitor**         | Collect and analyze telemetry        |
| **Log Analytics**         | Query and analyze log data           |
| **Alerts**                | Notify on conditions or events       |
| **Azure Service Health**  | View status of Azure services        |
| **Azure Resource Health** | Check health of individual resources |
| **Azure Automation**      | Automate and schedule tasks          |

---
