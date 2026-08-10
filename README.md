# FM Liquidation E-Commerce Platform 🚀

> **Note on Repository Access:** The full source code for this production-ready application is hosted in a private repository to protect proprietary business logic, system architecture, and configuration data. Full code access can be securely granted to recruiters, hiring managers, or interviewers upon request. Please contact me at info@edgehit.ca or via linkedin.com/in/femiag   .

---

## 💡 Project Overview
This is a production-ready, full-stack e-commerce application built specifically for a tool liquidation business. The platform dynamically handles unpredictable liquidation inventory, applies tiered shipping logic, ensures Canadian tax compliance, and features a secure, private administrative dashboard for rapid inventory updates.

---

## 📱 Previews & Media

<img width="1380" height="1151" alt="Screenshot 2026-08-10 at 5 55 44 PM" src="https://github.com/user-attachments/assets/be45b340-2416-40a7-ae43-93984b4b7b8e" />
<img width="1279" height="1121" alt="Screenshot 2026-08-10 at 6 00 26 PM" src="https://github.com/user-attachments/assets/65699b4f-7925-4333-9be6-d61fdc6a5a55" />
<img width="1382" height="1067" alt="Screenshot 2026-08-10 at 6 01 29 PM" src="https://github.com/user-attachments/assets/1b546371-3b13-4fbf-947c-3b2046869c18" />


---

## 🛠️ Tech Stack & Core Technologies
This application is built on a modern, edge-ready architecture designed for maximum performance, type safety, and transactional reliability:

* **Framework:** Next.js (App Router) – Powering both the responsive frontend UI and high-performance server-side API routes.
* **Language:** TypeScript – Providing strict type safety to eliminate runtime errors across critical shopping cart and checkout flows.
* **Styling:** Tailwind CSS – Utility-first layout engine driving a fully responsive, modern storefront.
* **State Management:** Zustand – Managing global shopping cart state with local storage persistence to prevent data loss on page refresh.
* **Database:** PostgreSQL – Relational database model managing core product templates mapping to real-time inventory conditions.
* **Backend Utilities & Storage:** Supabase – Securing the administrative dashboard via robust authentication and providing scalable bucket storage for media assets.
* **Payments:** Stripe – Processing secure checkout sessions using cryptographically signed webhooks.

---

## 🏆 Key Features & Engineering Challenges Solved

### 1. Concurrency Control ("Double-Sell" Protection)
In tool liquidation, inventory is often unique or highly limited. To prevent two users from checking out with the same physical item simultaneously, the backend utilizes secure **Stripe Webhooks** listening for transaction success events. The system deducts the precise database inventory identifier the exact millisecond a payment clears, ensuring high transactional integrity.

### 2. Smart Tiered Shipping Engine
The shopping cart automatically evaluates all active items to detect the highest shipping constraint (`small`, `standard`, `heavy`). It dynamically calculates a baseline rate, applies incremental handling fees for multi-item orders, and intelligently flags orders requiring physical freight pick-up.

### 3. Canadian Tax Compliance
The platform natively handles e-commerce taxation guidelines, automatically calculating and injecting the 13% Ontario HST across both product subtotals and dynamic shipping fees prior to transmitting data to the secure payment gateway.

### 4. High-Efficiency Admin CRUD Operations
Built a secure internal dashboard bypassing global caching mechanisms to ensure real-time inventory accuracy for warehouse personnel. Staff can instantly spin up new product listings, upload imagery directly to object storage buckets, and manage pricing variables without writing data scripts.

---

## 📈 Future Improvements & Scalability Roadmap
As the platform scales to support business growth, the following phases are scheduled for integration:
1. **International Expansion:** Upgrading gateway configurations to handle cross-border trade spanning North America (CA/US/MX) alongside automated currency conversion.
2. **Live Carrier APIs:** Transitioning from static tiered shipping formulas to real-time API queries via localized shipping brokers (e.g., Canada Post / Shippo) for dimension-based calculation.
3. **Automated Transactional Pipelines:** Integrating email services (SendGrid/Resend) to deliver programmatic PDF invoices and local warehouse pickup coordination details.
4. **Customer Auth Portals:** Introducing persistent consumer accounts where repeat buyers can evaluate historical orders and manage saved delivery parameters.
