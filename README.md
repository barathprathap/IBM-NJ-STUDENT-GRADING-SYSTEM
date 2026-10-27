<div align="center">

# 🚢 Swift Ship Tracker
### *Enterprise Logistics & Consignment Lifecycle Management in Salesforce CRM*

![Salesforce](https://img.shields.io/badge/Platform-Salesforce%20Lightning-00A1E0?style=for-the-badge&logo=salesforce&logoColor=white)
![Automation](https://img.shields.io/badge/Automation-Schedule--Triggered%20Flow-0176D3?style=for-the-badge&logo=salesforce&logoColor=white)
![Status](https://img.shields.io/badge/Build-Active%20%26%20Verified-2e7d32?style=for-the-badge)
![UI](https://img.shields.io/badge/UI%20Theme-Executive%20Dark-512da8?style=for-the-badge)

</div>

---

## 📊 Live Operations Dashboard

<div align="center">

![Swift Ship Tracker Dashboard](screenshots/dashboard.png)

</div>

> ⚡ **Real-time telemetry console** monitoring fleet fulfillment velocity, consignment progress across delivery hubs, and live active cargo manifests.

---

## 🎯 Project Overview

In conventional logistics environments, managing consignments across multiple routes using manual spreadsheets creates communication delays, overlooked delivery deadlines, and zero real-time visibility.

**Swift Ship Tracker** brings order to freight operations by consolidating consignments inside a centralized Salesforce Lightning architecture. The platform automates overdue tracking in the background and delivers actionable KPI metrics to dispatch teams.

---

## ⚡ Key Highlights & Capabilities

### 🏷️ 1. Automated Tracking Identity
Every record is cataloged with a unique, auto-sequenced consignment number (`SH-0001`, `SH-0002`, `SH-0003`, `SH-0004`) tied to customer metadata and origin-to-destination routing.

### 🔄 2. Dynamic Lifecycle Management
Consignments advance through five strict operational stages:

| Stage | Visual Indicator | Definition |
| :--- | :--- | :--- |
| **Pending** | `🟡 Pending` | Order placed, cargo being assembled at source warehouse |
| **Dispatched** | `🔵 Dispatched` | Cargo has cleared the dock and departed the facility |
| **In Transit** | `🟣 In Transit` | Carrier is actively moving between destination hubs |
| **Delivered** | `🟢 Delivered` | Consignment successfully acknowledged by recipient |
| **Delayed** | `🔴 Delayed` | Target delivery SLA deadline missed |

### ⚙️ 3. Autonomous SLA Breach Detection
A native background automation engine powered by a **Schedule-Triggered Flow** (`Mark_Overdue_Shipments`):
* 🕒 Runs automatically on a daily schedule.
* 🔍 Scans active consignments where `Shipment_Status__c != 'Delivered'`.
* ⏱️ Compares `Expected_Delivery_Date__c` against the runtime date (`$Flow.CurrentDate`).
* 🚨 Proactively transitions past-due shipments to **Delayed** without requiring manual agent checks.

### 📈 4. Executive Analytics Console
* 📦 **Total Shipments:** Live volume counter displaying current active consignments.
* 🧭 **Active Delivery Velocity:** Speedometer gauge visualizing operational delivery pace.
* 🍩 **Fulfillment Pipeline:** Color-coded donut chart highlighting milestone breakdown.
* 📊 **Consignments by Status & Hub:** Grouped bar chart comparing load across routes (Chennai, Mumbai, Delhi, Bengaluru).
* 📋 **Live Shipment Manifest:** Full-width record ledger tracking tracking numbers, clients, dispatch dates, and target deadlines.

---

## 🗄️ Custom Schema Design (`Shipment__c`)

| Field Label | API Name | Data Type | Key Purpose |
| :--- | :--- | :--- | :--- |
| **Shipment Number** | `Name` | `Auto Number (SH-{0000})` | System-generated tracking ID |
| **Customer Name** | `Customer_Name__c` | `Text (100)` | Consignment recipient / receiving entity |
| **Destination** | `Destination__c` | `Text (100)` | Target arrival transit hub / city |
| **Dispatch Date** | `Dispatch_Date__c` | `Date` | Actual departure date from dispatch center |
| **Expected Delivery Date** | `Expected_Delivery_Date__c` | `Date` | Contractual delivery SLA target |
| **Shipment Status** | `Shipment_Status__c` | `Picklist` | Active delivery stage progression |

---

## 👥 Project Team & Contributors

| Member Name | Role / Focus Area | Contact / Handle |
| :--- | :--- | :--- |
| **Barath Prathap** | Project Lead & Salesforce Architecture | [@barathprathap](https://github.com/barathprathap) |
| **Teammate 2** | Declarative Automation & Flow Logic | Team Member |
| **Teammate 3** | Object Schema & Data Modeling | Team Member |
| **Teammate 4** | Lightning Reports & Dashboard Analytics | Team Member |

---

<div align="center">

*Swift Ship Tracker — Built on Salesforce Lightning Platform*

</div>
