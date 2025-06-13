---

# 🧾 **Azure Compute Cheat Sheet – Bullet Point Quick Tips (AZ-900)**

---

## ✅ **Core Azure Compute Services**

### 💻 **Azure Virtual Machines (VMs)** – *IaaS*

* You manage: OS, apps, patches, security.
* Great for **legacy apps**, **custom software**, or **lift-and-shift** scenarios.
* **Pricing** based on VM size, OS, storage, and region.
* Supports **availability sets**, **zones**, and **scale sets**.

### VM Series (What to Remember):

* **B-series**: Burstable workloads.
* **D-series**: General purpose (web servers, databases).
* **E-series**: Memory optimized (SQL, cache).
* **F-series**: Compute optimized (CPU-heavy).
* **Lsv2-series**: Storage optimized (high IOPS).
* **N-series**: GPU (AI, ML, rendering).
* **M-series**: High memory (SAP).

---

### 🌐 **Azure App Service** – *PaaS*

* Host web apps and APIs.
* Supports .NET, Node.js, Java, Python, PHP, and more.
* **App Service Plan** determines:

  * Region
  * Pricing tier
  * Scaling (manual/auto)
* **Multiple apps** can share the same App Service Plan.

#### App Service Plan Tiers:

* **Free/Shared** – Dev/test only
* **Basic** – Manual scale
* **Standard** – Auto-scale + staging
* **Premium** – Faster & more scalable
* **Isolated** – Secure, in VNet

---

### 📦 **Azure Container Instances (ACI)**

* Run containers **without managing servers**.
* **No orchestration** (single container or simple groups).
* Best for **quick tasks**, **jobs**, or **APIs**.
* Pay **per second** of CPU/memory used.

---

### 🚢 **Azure Kubernetes Service (AKS)**

* Managed Kubernetes to run **containerized microservices**.
* Azure manages the master nodes.
* Supports **auto-scaling**, **updates**, and **RBAC**.
* Best for **complex, production-grade container workloads**.

---

### ⚡ **Azure Functions** – *Serverless*

* **Event-driven code** execution (e.g. timers, HTTP triggers).
* **Scales automatically** based on events.
* **Billing**: Pay only for executions and runtime.

#### Max Execution Time:

* **Consumption plan**: 5 minutes (extendable to 10)
* **Premium/Dedicated**: Unlimited

---

### 🧑‍💻 **Azure Virtual Desktop (AVD)**

* Host **Windows desktops** in the cloud.
* Accessible from anywhere.
* Integrates with Microsoft 365 and Azure AD.
* Useful for **secure remote access** or **centralized desktops**.

---

### 🧮 **Azure Batch**

* Run **large-scale batch or parallel jobs**.
* Automatically provisions and manages compute.
* Ideal for **rendering, modeling, simulations**.
* Works with **custom scripts, containers, and apps**.

---

## 🛡️ **High Availability & SLAs**

| Service                  | SLA    |
| ------------------------ | ------ |
| VM + Availability Set    | 99.95% |
| VM + Availability Zones  | 99.99% |
| App Service (Standard+)  | 99.95% |
| Functions (Premium Plan) | 99.95% |
| AKS Nodes                | 99.95% |

> 🧠 Free tiers **don’t have an SLA**!

---

## 📊 **Scaling Options**

| Service     | Scaling                          |
| ----------- | -------------------------------- |
| VMs         | Manual or auto (with Scale Sets) |
| App Service | Manual or auto (Standard+)       |
| AKS         | Auto-scaling with node pools     |
| Functions   | Auto-scale (by default)          |
| ACI         | Manual per container group       |

---

## 💰 **Compute Pricing Models**

* **VMs**: Per second; price varies by region and specs.
* **App Service**: Based on App Service Plan.
* **ACI / Functions**: Per execution (true pay-per-use).
* **AVD**: Per user and VM usage.
* **AKS**: Pay for agent nodes (control plane is free).
* **Batch**: Depends on the VM resources used.

---

## 🔐 **Security & Identity**

* Use **Azure AD + RBAC** to control access to compute resources.
* Apply **NSGs** (Network Security Groups) to protect VMs.
* **App Service** and **Functions** support **managed identities**.

---

## 🌍 **Hybrid & Management Tools**

* **Azure Arc**: Manage on-prem VMs & Kubernetes like Azure resources.
* **Management Tools**:

  * Azure Portal (GUI)
  * Azure CLI / PowerShell
  * ARM Templates or Bicep (Infrastructure as Code)

---

## 📌 **Exam Tips (AZ-900 Specific)**

* Know the **difference between IaaS, PaaS, Serverless**.
* Expect **scenario-based questions**: “Which service should you choose if…”
* Memorize **SLA levels and scaling capabilities**.
* Understand **when to use each compute service** and its **pricing implications**.

---
