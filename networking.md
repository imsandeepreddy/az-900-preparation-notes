---

# 🌐 **Azure Networking – AZ-900 Complete Cheat Sheet**

---

## 🔹 1. **Azure Virtual Network (VNet)**

* Creates a **private, isolated network** in Azure (like your on-prem LAN).
* Connects Azure resources like **VMs, App Services, DBs** securely.
* **Supports**:

  * **Subnets** – divide the VNet for isolation (e.g., web, app, DB tiers).
  * **Private IPs** – for internal communication.
  * **Public IPs** – to expose to internet (e.g., web servers).
  * **VNet Peering** – connects VNets across same or different regions.
  * **Service Endpoints** – secure direct access to Azure services.
  * **Private Endpoints** – access Azure PaaS services via **private IPs**.

---

## 🔹 2. **Network Security Groups (NSGs)**

* Acts like a **firewall** for VNets.
* Controls **inbound/outbound traffic** to subnets or NICs (VMs).
* NSG Rules include:

  * **Priority** (lower = higher priority)
  * **Source/Destination**
  * **Port & Protocol**
  * **Action**: Allow/Deny
* Default rules allow VNet traffic and block inbound from the internet.
* Best Practice: Apply NSGs at **subnet** for broader control, and **NIC** for precision.

---

## 🔹 3. **Azure Application Gateway**

* A **Layer 7 load balancer** – smart routing for **HTTP/HTTPS** traffic.
* Key features:

  * **Path-based routing** (`/api`, `/images`, etc.)
  * **Multi-site hosting** (e.g., host multiple domains)
  * **SSL termination** (TLS offloading at gateway)
  * **Web Application Firewall (WAF)**:

    * Protects against OWASP Top 10 attacks
    * Modes: **Detection** or **Prevention**
* Use for **web apps that need advanced routing and security**.

---

## 🔹 4. **Other Load Balancing Services**

| Service                       | Layer       | Description                                        |
| ----------------------------- | ----------- | -------------------------------------------------- |
| **Azure Load Balancer**       | L4          | TCP/UDP traffic distribution (VMs, databases)      |
| **Azure Application Gateway** | L7          | Smart HTTP(S) routing + WAF                        |
| **Azure Traffic Manager**     | DNS         | Routes based on performance, priority, geography   |
| **Azure Front Door**          | L7 (Global) | Global HTTP(S) load balancing + acceleration + WAF |

📌 *Use Front Door for fast, global web app delivery. Use Traffic Manager to route DNS to different regions.*

---

## 🔹 5. **Connectivity Options**

| Option           | Description                                                             |
| ---------------- | ----------------------------------------------------------------------- |
| **VPN Gateway**  | Secure tunnel over public internet to Azure (IPSec)                     |
| **ExpressRoute** | Private, dedicated fiber connection from on-prem to Azure               |
| **VNet Peering** | Private, high-speed connection between VNets (same or different region) |

📌 *Use ExpressRoute for high-security or regulatory needs. Use VPN Gateway for cost-effective hybrid setup.*

---

## 🔹 6. **Security Services in Networking**

* **NSGs**: Filter traffic to/from VMs or subnets.
* **Azure Firewall**: Stateful firewall with logging, application rules, FQDN filtering.
* **DDoS Protection**:

  * **Basic**: Included with all VNets.
  * **Standard**: Adds telemetry, tuning, and alerting for high-risk apps.

---

## 🔹 7. **Performance & Delivery Services**

| Service             | Function                                                   |
| ------------------- | ---------------------------------------------------------- |
| **CDN**             | Content Delivery Network – caches static content at edge   |
| **Front Door**      | Global entry point for web apps with TLS, WAF, and caching |
| **Traffic Manager** | DNS-based routing for cross-region app access              |

📌 *Use CDN for static content (images, videos). Use Front Door for global web app acceleration.*

---

## 🔹 8. **Key Comparisons**

### 🔄 VNet vs NSG vs App Gateway

| Feature           | VNet                | NSG                | App Gateway               |
| ----------------- | ------------------- | ------------------ | ------------------------- |
| Purpose           | Network container   | Traffic control    | Smart web traffic routing |
| Layer             | N/A                 | Layer 3/4          | Layer 7                   |
| Use Case          | Deploy VMs, subnets | Allow/deny traffic | Host secure web apps      |
| Configurable With | Subnets, IPs        | Rules for ports    | Backend pools, listeners  |
| Internet Exposure | Optional            | Controlled         | Public/Private options    |

---

## 🔹 9. **Pricing & SLAs (What to Remember)**

| Service       | Billing Model             | SLA (approx.) |
| ------------- | ------------------------- | ------------- |
| VNet          | Free (mostly)             | N/A           |
| NSG           | Free                      | N/A           |
| VPN Gateway   | Based on bandwidth        | 99.9%         |
| ExpressRoute  | Per circuit               | 99.95%        |
| Load Balancer | Free/Standard tiers       | 99.99%        |
| App Gateway   | Per-hour + data processed | 99.95%        |
| Front Door    | Per request + data        | 99.99%        |
| Firewall      | Per-deployment + data     | 99.95%        |

---

## 🔹 10. **AZ-900 Quick Exam Tips for Networking**

✅ **Understand these well**:

* VNet basics, subnets, private vs public IP
* NSG rules and their purpose
* App Gateway vs Load Balancer vs Front Door
* VPN vs ExpressRoute vs Peering
* When to use WAF (App Gateway or Front Door)
* Private Endpoints for secure PaaS access
* Traffic Manager = DNS-based routing only (not real-time load balancer)

✅ **Expect scenario-based questions**, such as:

> "Your company needs to route traffic to the closest region based on latency."
> ✅ Use: **Traffic Manager (performance-based routing)**

> "You need to allow port 3389 (RDP) to a VM only from your IP."
> ✅ Use: **NSG with inbound rule to VM's NIC**

> "Secure connection between on-prem data center and Azure with high reliability."
> ✅ Use: **ExpressRoute**

---
