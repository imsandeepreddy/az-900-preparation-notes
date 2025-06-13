---

# 🗄️ **Azure Storage – AZ-900 Cheat Sheet (Quick Tips & Bullet Style)**

---

## ✅ **1. Core Azure Storage Services**

| Storage Type                   | Use Case                                                | Access                  |
| ------------------------------ | ------------------------------------------------------- | ----------------------- |
| **Blob Storage**               | Store unstructured data (images, videos, backups, logs) | REST APIs, SDKs         |
| **File Storage (Azure Files)** | Shared file systems (like network drives)               | SMB, NFS                |
| **Disk Storage**               | OS and data disks for VMs                               | Attached to VMs         |
| **Queue Storage**              | Messaging between apps                                  | FIFO queues             |
| **Table Storage**              | NoSQL key-value storage                                 | Lightweight, fast reads |

---

## 🔷 **2. Azure Blob Storage** (Most Tested)

* Stores **unstructured data** (images, videos, logs, backups, big data).
* Access via **HTTP/HTTPS**, REST API, SDKs.
* Supports **tiers** for cost management:

  * **Hot**: Frequently accessed (higher cost).
  * **Cool**: Infrequently accessed (cheaper storage, higher access cost).
  * **Archive**: Rarely accessed (very cheap, high latency to retrieve).

📌 **Blob Types**:

* **Block blob**: Large files, binary data (e.g., videos, documents)
* **Append blob**: Ideal for logs
* **Page blob**: Used for Azure VM disks

---

## 📁 **3. Azure File Storage**

* Fully managed **shared file system** in the cloud.
* Access via **SMB or NFS protocols** (mountable on Windows, Linux, macOS).
* **Azure File Sync** lets you **cache Azure Files on on-prem servers** (hybrid scenario).

📌 Use when you need:

* Traditional file shares
* Cloud backup for on-prem file servers
* Centralized storage accessible by many VMs

---

## 💽 **4. Azure Disk Storage**

* Provides persistent **block-level storage** for Azure VMs.
* Types:

  * **OS Disk** – VM boot volume
  * **Data Disk** – Additional attached storage
* Performance Tiers:

  * **Standard HDD**: Low-cost, low-performance
  * **Standard SSD**: Better performance, still low-cost
  * **Premium SSD**: High-performance workloads (databases, production)
  * **Ultra Disk**: Extreme performance (high IOPS), very expensive

📌 Attached **only to VMs**.

---

## 📨 **5. Azure Queue Storage**

* Stores **messages** for reliable communication between services.
* Supports **millions of messages**, up to 64KB each.
* Used in **asynchronous messaging scenarios** (like microservices).

📌 Use to **decouple app components** and ensure **resilient workflows**.

---

## 🔑 **6. Azure Table Storage**

* **NoSQL key-value store** for structured, non-relational data.
* Fast, cheap, and simple.
* Use for:

  * Storing metadata
  * App settings
  * Sensor or IoT data

📌 **Schema-less**, highly scalable, and lower-cost than traditional databases.

---

## 💾 **7. Storage Account Types**

| Type                          | Purpose                                              |
| ----------------------------- | ---------------------------------------------------- |
| **General Purpose v2 (GPv2)** | Most common. Supports all storage types and features |
| **Blob Storage Account**      | Only for Blob data (legacy; now GPv2 preferred)      |
| **FileStorage Account**       | High-performance Azure Files                         |
| **BlockBlobStorage Account**  | High-performance for block blobs                     |

📌 Always prefer **GPv2** unless there's a specific performance need.

---

## 🔐 **8. Security & Access Control**

* **Encryption at rest** by default (using Azure-managed keys or customer-managed keys).
* Supports **HTTPS** for secure data transfer.
* **Shared Access Signature (SAS)**: Grants limited-time, scoped access to storage resources.
* **Azure AD** integration for identity-based access control (e.g., RBAC).
* **Private Endpoints**: Secure access to storage over VNet (no public IP).

---

## 🧪 **9. High Availability & Redundancy Options**

| Redundancy Option                   | Description                          |
| ----------------------------------- | ------------------------------------ |
| **LRS (Locally Redundant Storage)** | 3 copies in one data center          |
| **ZRS (Zone-Redundant Storage)**    | 3 copies across Availability Zones   |
| **GRS (Geo-Redundant Storage)**     | Copies in primary + secondary region |
| **RA-GRS**                          | GRS + Read access to secondary       |

📌 Choose **ZRS** or **GRS** for critical data. LRS is cheapest but least resilient.

---

## 💰 **10. Storage Pricing Model**

* Based on:

  * **Type of storage** (Blob, File, etc.)
  * **Storage tier** (Hot, Cool, Archive)
  * **Operations** (read/write/delete)
  * **Data transfer (egress)**

📌 **Hot = expensive to store, cheap to access**
📌 **Archive = cheap to store, expensive to access**

---

## ⚙️ **11. Management Tools**

* **Azure Portal**: GUI-based management.
* **Azure Storage Explorer**: Desktop tool to manage blobs, files, queues.
* **Azure CLI / PowerShell**: For scripted management.
* **ARM Templates / Bicep**: For infrastructure as code.

---

## ✅ **AZ-900 Key Storage Use Cases (Match the Service)**

| Scenario                          | Use This      |
| --------------------------------- | ------------- |
| Store large files (images/videos) | Blob Storage  |
| Shared network drive for VMs      | Azure Files   |
| Disk for a VM                     | Disk Storage  |
| App messaging system              | Queue Storage |
| Store key-value data cheaply      | Table Storage |

---

## 🧠 **Final Exam Tips for Azure Storage (AZ-900)**

* Know **Blob tiers (Hot, Cool, Archive)** and their tradeoffs.
* Understand **redundancy levels**: LRS vs ZRS vs GRS.
* Know **what storage type fits what scenario**.
* Know what **Shared Access Signature (SAS)** is for.
* Expect questions like:

  > "Which storage solution provides access over SMB protocol?"
  > ✅ **Azure Files**

  > "Which tier is cheapest for rarely accessed data?"
  > ✅ **Archive**

  > "How do you secure access to Azure Storage from a VNet?"
  > ✅ **Private Endpoint**

---
