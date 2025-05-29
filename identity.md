---

# 🧾 **Azure Identity – AZ-900 Cheat Sheet (Quick Tips & Bullet Style)**

---

## 🔹 1. **Azure Active Directory (Azure AD)**

### 🔐 What Is It?

Azure AD is Microsoft’s **cloud-based identity and access management (IAM)** service.
It helps employees sign in and access:

* Microsoft 365
* Azure portal
* Custom apps
* Thousands of SaaS apps

> Think of it as the **cloud version of Active Directory**, but **not a 1-to-1 replacement** of on-prem AD.

---

### 🔑 Key Features:

* **Single Sign-On (SSO)**: One login for all apps and services.
* **Authentication**: Username + password, MFA, biometrics.
* **Authorization**: What users are allowed to do (via RBAC).
* **Device registration**: Manage mobile and PCs.
* **Conditional Access**: Enforce policies based on location, device, etc.

---

### ✅ Common Azure AD Objects:

| Object                 | Description                                    |
| ---------------------- | ---------------------------------------------- |
| **Users**              | People with login access                       |
| **Groups**             | Collection of users                            |
| **Applications**       | Registered apps (e.g., SaaS or custom)         |
| **Service Principals** | Identity for apps/services to access resources |

---

### 💡 Exam Tip:

> "Which service handles user authentication in Azure?"
> ✅ **Answer: Azure Active Directory**

---

## 🔹 2. **Role-Based Access Control (RBAC)**

### 🔒 What is RBAC?

Controls **what users can do** with Azure resources.

> Identity = **who**
> RBAC = **what they’re allowed to do**

---

### 🧩 RBAC Components:

| Component              | Description                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| **Security Principal** | User, group, service principal, or managed identity                                       |
| **Role Definition**    | Collection of permissions (e.g., Reader, Contributor)                                     |
| **Scope**              | Level at which role applies (Management Group → Subscription → Resource Group → Resource) |
| **Role Assignment**    | Binds a principal to a role at a scope                                                    |

---

### 🔑 Built-in Roles to Know:

| Role                          | Permissions                      |
| ----------------------------- | -------------------------------- |
| **Owner**                     | Full access + manage access      |
| **Contributor**               | Full access, can't manage access |
| **Reader**                    | View-only                        |
| **User Access Administrator** | Manage RBAC permissions          |

📌 You can also create **custom roles**, but that's **not on AZ-900**.

---

## 🔹 3. **Multi-Factor Authentication (MFA)**

### 🛡️ What is MFA?

Requires **two or more authentication methods**:

* Password
* OTP (phone/email)
* Biometrics (Windows Hello, Authenticator app)

📌 Enabled via **Azure AD** → Free tier includes **MFA for admins** by default.

---

## 🔹 4. **Conditional Access**

### 🚦 What is it?

Azure AD feature to apply **rules and policies based on conditions**, like:

* User/group
* Device type
* Location (IP)
* App being accessed

> Example: Require MFA if login is from a new country.

---

## 🔹 5. **Identity Protection (Premium P2 Feature)**

### 🧠 What is it?

Uses **AI and machine learning** to detect risky sign-ins and risky users.

Can automatically:

* Block sign-ins
* Force password resets
* Trigger conditional access

📌 Available in **Azure AD Premium P2**, not on the free tier.

---

## 🔹 6. **Azure AD Join vs. Hybrid Join**

| Type              | Use Case                                                      |
| ----------------- | ------------------------------------------------------------- |
| **Azure AD Join** | Devices joined directly to Azure AD (cloud-only environments) |
| **Hybrid Join**   | Devices joined to **on-prem AD + Azure AD** (for hybrid orgs) |

---

## 🔹 7. **Managed Identities**

* Automatically manage identities for **Azure resources** (like VMs or App Services).
* Used to **access other Azure services** securely (like Azure Key Vault) without storing credentials.

📌 Available in **System-assigned** (1:1) or **User-assigned** (reusable across resources).

---

## ✅ **AZ-900 Quick Identity Scenarios**

| Scenario                                              | Service             |
| ----------------------------------------------------- | ------------------- |
| Authenticate users across cloud apps                  | Azure AD            |
| Give a developer read-only access to a resource group | RBAC – Reader role  |
| Require a second factor to access the Azure Portal    | MFA                 |
| Restrict access by location                           | Conditional Access  |
| Automatically detect and respond to risky logins      | Identity Protection |
| Allow a VM to access a Key Vault securely             | Managed Identity    |

---

## 🧠 Final Exam Tips for Azure Identity

* Know **Azure AD is used for authentication and SSO**.
* **RBAC** = Authorization at scope levels (Subscription → Resource Group → Resource).
* MFA is a **common security feature**. It **protects against stolen credentials**.
* Conditional Access lets you create **smart access policies**.
* Managed Identity = **No secrets or credentials needed** for resource-to-resource access.

---
