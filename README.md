💊 Pharmacy Management System – PL/SQL Oracle Database Project

### 👤 Student Info
- **Name:** Muneza Pascal   
- **Student ID:** 26630  
- **Course:** Database Development with PL/SQL (INSY 8311)  
- **Lecturer:** Eric Maniraguha  
- **Academic Year:** 2024–2025
  
🧠 Introduction:


Modern pharmacies face increasing challenges due to manual processes that often result in prescription errors, inventory mismatches, delayed patient services, and data inconsistencies. 
To address these pain points, this project introduces a Pharmacy Management System built using Oracle Database and PL/SQL programming. The system provides automation, real-time tracking, and secure data management for prescriptions, inventory, and payments—enhancing service delivery and operational efficiency.

The project was implemented in eight phases, covering everything from problem analysis and business modeling to logical design, implementation, testing, and reporting.

📅 Project Timeline and Structure

Phase | Title
 
- **(Phase 1: 🎯 Problem Statement).** **Identifying Core Challenges** – Pinpointing the key pharmacy pain points (prescription errors, stock mismatches, billing delays) and defining exactly what our system must solve.
- **(Phase 2: 🛠 Business Process Modeling).** **Mapping Essential Workflows** – Drawing a clear flowchart of prescription issuance → validation → dispensing → billing → stock update, and assigning who does each step.
- **(Phase 3: 🧩 Logical Model Design).** **Designing Strong Foundations** – Translating workflow into tables (Patients, Doctors, Medicines, Prescriptions, Payments), defining fields and relationships to ensure clean, normalized data.
- **(Phase 4: 🏗️ Physical Database Implementation).**  **Building the Database** – Creating the Oracle pluggable database (mon_26630_pascal_pharmacy_db), setting up user privileges, and connecting Oracle Enterprise Manager for real-time monitoring.
- **(Phase 5: 🧪 Data Insertion).**  **Populating with Meaningful Data** – Loading realistic sample records (patients, doctors, medicines, prescriptions, payments) to validate constraints and simulate real-world operations.
- **(Phase 6: 🔄 Transaction Handling).**  **Ensuring Data Integrity** – Writing PL/SQL procedures, functions, and packages for core actions (issue prescription, process payment), using cursors and exception blocks to keep data accurate.
- **(Phase 7: 🔐 Security Features).** **Securing Sensitive Information** – Implementing triggers to auto-update stock and block changes on weekdays/holidays, plus audit tables and triggers to log every data-change attempt.
- **(Phase 8: 📊 Reporting and Query Optimization).**  **Delivering Actionable Insights** – Crafting analytical queries (low-stock alerts, sales summaries), tuning indexes for speed, and preparing final reports and a 10-slide presentation for stakeholders.

**#🎯 Phase 1: Problem Statement.**

**###🧩 Problem Definition**

Pharmacies often face operational inefficiencies due to manual handling of prescriptions, outdated inventory tracking methods, and unstructured patient records. These issues contribute to:

--Medication errors and mismatched prescriptions

- Delays in service

- Out-of-stock problems

- Lost revenue due to poor billing and payment tracking

### 🧪 Context

This Pharmacy Management System is designed for community and hospital-based pharmacies where data integrity, automation, and quick access to patient information are critical.

👥 Target Users

Pharmacists – Manage inventory, fulfill prescriptions

Doctors – Issue prescriptions

Patients – Get medication, view history

Managers – View analytics, track performance

### 🎯 Project Goals

- Automate prescription workflows

- Track inventory levels and alert on low stock
  
 ---

# 🛠️ Phase 2: Business Process Modeling (BPM)

### 📌 What This Phase Covers
You’ll map out how your pharmacy operations should work—step by step—so you can spot exactly where to automate and optimize.

### 🎯 Scope & Objectives
Scope: Prescription lifecycle, from doctor’s order through dispensing and billing.

Objective: Create a clear, visual model (using BPMN or UML) that shows every actor, decision point, and system action. 

### 🧑‍🤝‍🧑 Actors & Their Roles

- **Doctor:** Issues a prescription

- **Patient:** Receives prescription and requests medication

- **Pharmacist:** Validates prescription, dispenses medicine, initiates billing.

- **System:**Checks stock, updates inventory, processes payment, sends alerts.

### 🔁 Key Workflows

1. **Prescription Issuance:** Doctor prescribes medicine to patient.

2. **Validation & Veryfiation:** 
    . Pharmacist retrieves the order, checks for completeness/legibility.

  .  System verifies patient eligibility and payment status.
  
4. **Stock Check:**
    . System automatically confirms medicine availability.

   . If out of stock → trigger back-order or low-stock alert.
   
5. **Dispensing & Billing:**
  . Pharmacist dispenses the medicine.

 . System calculates cost, records payment method, and issues receipt.
 
7. **Inventory Update & Notification:**

  . System deducts dispensed quantity from stock.

  . Alerts sent if stock falls below reorder threshold.

  ### 🏷️ Use of Swimlanes

* 📘 **Doctor Lane:**  
  - Creates and submits the electronic prescription.  

* 📙 **Patient Lane:**  
  - Receives notifications (e.g., “Prescription ready for pickup”).  
  - Provides any additional info if needed (e.g., insurance details).  

* 📗 **Pharmacist Lane:**  
  - Retrieves and validates the prescription.  
  - Dispenses medicine and hands it over to the patient.  
  - Initiates billing and confirms payment.  

* 📔 **System Lane:**  
  - Checks medicine stock and availability.  
  - Updates inventory quantities automatically.  
  - Processes payment and issues receipts.  
  - Sends low-stock alerts or back-order notifications.  


### 🔄 Logical Flow Description

Start: Doctor logs into system → enters prescription.

Decision: System checks patient record → if invalid, notify pharmacist → end.

Action: Pharmacist verifies prescription details.

Decision: System checks stock → if available, proceed; if not, send low-stock alert.

Action: Pharmacist dispenses medicine → system records transaction.

Action: System updates inventory and processes payment.

End: Patient is notified that prescription is fulfilled.

📊 Deliverable
A BPMN diagram (in Lucidchart or draw.io) that depicts the above swimlanes, workflows, decision points, and system actions.

A brief write-up (1/2 page) explaining each step and how it aligns with MIS principles (e.g., decision support, data flow, exception handling). 

Tip: Keep your diagram clean—use standard BPMN symbols (events, tasks, gateways) and label every arrow with the trigger or data passed.

# 🗂 Phase 3: Logical Model Design for Pharmacy Management System

## 📠 What This Phase Covers
This phase focuses on designing a detailed and robust logical data model for the pharmacy management system. The goal is to create a structure that accurately represents entities, their attributes, and relationships while ensuring the design can handle real-world pharmacy data scenarios.

## 📌 Entities and Attributes

### 1. 🧑‍⚕️ **Doctor**:
* **Attributes:** `Doctor_ID (PK)`, Name, Specialization, Contact_Info, License_Number
* Linked to Prescriptions via `Doctor_ID (FK)`

### 2. 👤 **Patient**:
* **Attributes:** `Patient_ID (PK)`, Name, DOB, Address, Phone, Email, Insurance_Info, Medical_History
* Linked to Prescriptions and Payments

### 3. 💊 **Medicine**:
* **Attributes:** `Medicine_ID (PK)`, Name, Description, Manufacturer, Category, Unit_Price, Current_Stock, Reorder_Level, Expiry_Date
* Linked to Prescription_Items via `Medicine_ID (FK)`

### 4. 📝 **Prescription**:
* **Attributes:** `Prescription_ID (PK)`, `Doctor_ID (FK)`, `Patient_ID (FK)`, Issue_Date, Status
* Links Doctors to Patients and connects to Prescription_Items

### 5. 📋 **Prescription_Items**:
* **Attributes:** `Item_ID (PK)`, `Prescription_ID (FK)`, `Medicine_ID (FK)`, Dosage, Quantity, Instructions
* Junction table connecting Prescriptions to Medicines

### 6. 👨‍💼 **Pharmacist**:
* **Attributes:** `Pharmacist_ID (PK)`, Name, License_Number, Contact_Info, Shift_Hours
* Linked to Dispensed_Medicines via `Pharmacist_ID (FK)`

### 7. 💼 **Dispensed_Medicines**:
* **Attributes:** `Dispensed_ID (PK)`, `Prescription_ID (FK)`, `Pharmacist_ID (FK)`, Dispensing_Date
* Tracks which pharmacist dispensed which prescription

### 8. 💵 **Payment**:
* **Attributes:** `Payment_ID (PK)`, `Prescription_ID (FK)`, Amount, Payment_Date, Payment_Method, Status
* Linked to Prescription via `Prescription_ID (FK)`

### 9. 📦 **Inventory_Log**:
* **Attributes:** `Log_ID (PK)`, `Medicine_ID (FK)`, Transaction_Type, Quantity, Transaction_Date
* Tracks all inventory changes (additions, deductions, adjustments)

## 🚦 Relationships and Cardinalities

### 🔄 Doctor (1) — (M) Prescription
* Each doctor can write multiple prescriptions, but each prescription is written by exactly one doctor.

### 🔄 Patient (1) — (M) Prescription
* Each patient can have multiple prescriptions over time, but each prescription belongs to exactly one patient.

### 🔄 Prescription (1) — (M) Prescription_Items 
* Each prescription can include multiple medicines, and each prescription item belongs to exactly one prescription.

### 🔄 Medicine (1) — (M) Prescription_Items
* Each medicine can appear in multiple prescriptions, and each prescription item refers to exactly one medicine.

### 🔄 Pharmacist (1) — (M) Dispensed_Medicines
* Each pharmacist can dispense multiple prescriptions, but each dispensed prescription is handled by exactly one pharmacist.

### 🔄 Prescription (1) — (1) Dispensed_Medicines
* Each prescription is dispensed exactly once, and each dispensing record refers to exactly one prescription.

### 🔄 Prescription (1) — (1) Payment
* Each prescription has exactly one payment record, and each payment is for exactly one prescription.

### 🔄 Medicine (1) — (M) Inventory_Log
* Each medicine can have multiple inventory transactions, but each inventory transaction involves exactly one medicine.

## ⚙️ Handling Data Scenarios

**The model is designed to handle:**

* **Multiple Medications Per Prescription**: The Prescription_Items table allows a single prescription to include multiple medicines with different dosages and instructions.

* **Prescription Status Tracking**: The Status attribute in Prescription table tracks whether it's new, validated, dispensed, or completed.

* **Inventory Management**: The Inventory_Log tracks all changes to medicine stock, enabling accurate stock levels and reorder alerts.

* **Payment Verification**: The Payment table with status field allows tracking whether payment has been completed before medicine dispensing.

* **Prescription Validation**: The relationship between Prescription and Dispensed_Medicines ensures prescriptions are properly validated and dispensed by qualified pharmacists.

* **Stock Thresholds**: Reorder_Level in the Medicine table triggers alerts when inventory falls below critical levels.

## 📊 Normalization and Constraints

* **First Normal Form (1NF)**: All tables have a primary key, and all attributes contain atomic values.

* **Second Normal Form (2NF)**: All non-key attributes are fully functionally dependent on the primary key.

* **Third Normal Form (3NF)**: No transitive dependencies exist, with junction tables (Prescription_Items) properly handling many-to-many relationships.

* **Referential Integrity**: Foreign key constraints ensure data consistency across related tables.

* **Data Validation**: Check constraints on critical fields like Medicine.Current_Stock (≥ 0) and Payment.Status.

## 📝 Benefits of This Logical Model

1. **Comprehensive Prescription Tracking**: Full lifecycle from creation to dispensing and payment
2. **Accurate Inventory Management**: Real-time stock tracking with detailed transaction history
3. **Clear Accountability**: Records which pharmacist handled each prescription
4. **Flexible Payment Handling**: Supports multiple payment methods and status tracking
5. **Regulatory Compliance**: Maintains complete records of prescriptions, practitioners, and dispensing details
6. **Scalability**: Design accommodates growth in prescription volume and medication inventory

This logical model provides a solid foundation for developing a reliable and efficient pharmacy management system that accurately represents the real-world processes captured in our business process model.


## 🏗️ Phase 4: Physical Database Implementation

### 🧱 Database Setup

- **Database Name:** `mon_26630_pascal_pharmacy_db`  
- **Password:** pascal  
- Created in **Oracle 19c** using **SQL Developer**  

### 📈 Monitoring

- **Oracle Enterprise Manager (OEM)** was used to monitor performance and activity.  
- Snapshots and performance dashboards help track real-time resource use and activity logs.

  
## 🧪 Phase 5: Data Insertion

### 📋 Sample Data

Realistic sample records were inserted into all tables:
- 10+ patients with medical histories  
- 5+ doctors with specialties  
- 15+ medicines with stock levels and pricing  
- 10+ prescriptions and payment records  

### 📌 Data Integrity

- Insert statements used with validation constraints  
- Referential integrity ensured via foreign keys  
- `CHECK`, `NOT NULL`, and `UNIQUE` constraints applied

## 🔄 Phase 6: Transaction Handling

### 📦 Stored Procedures & Functions

- **Procedures** to issue prescriptions and insert payments  
- **Functions** to calculate total price and fetch prescription details  
- All operations tested with realistic transaction sequences  

### 🔁 Cursors & Exception Handling

- Used **explicit cursors** to iterate through prescriptions  
- Built-in **exception blocks** handle duplicate entries or invalid inputs  

### 📦 Packages

- Reusable **packages** grouped business logic (e.g., billing, inventory update)


## 🔐 Phase 7: Security Features & Auditing

### 🔔 Triggers

- **BEFORE INSERT**: Auto-update stock when a medicine is prescribed  
- **AFTER UPDATE/DELETE**: Audit sensitive changes  

### 🚫 Restriction Logic

- Created a **trigger** to block `INSERT`, `UPDATE`, `DELETE` during weekdays and public holidays  
- Referenced a **holiday table** storing static dates for enforcement  

### 🛡️ Auditing

- Audited user actions on sensitive tables  
- Logged data includes:
  - **User ID**
  - **Action Date & Time**
  - **Operation Attempted**
  - **Status (Allowed / Denied)**
 


## 📊 Phase 8: Reporting and Query Optimization

### 📂 GitHub Report

The GitHub repository contains:
- SQL scripts (DDL, DML, Triggers, Procedures, Packages)
- Screenshot folder (OEM monitoring, data queries)
- This complete `README.md` documentation

### 📈 Reports & Queries

- Analytical queries for:
  - Low stock medicines
  - Total sales per doctor/patient
  - Daily revenue summaries  
- Indexed commonly queried fields for faster execution

### 🖥️ Presentation

A **10-slide PowerPoint presentation** summarizes:
- Project background
- System architecture
- Implementation steps
- Screenshots
- Results and future recommendations


## 🔚 Conclusion

The Pharmacy Management System demonstrates how database-driven automation can resolve real-world inefficiencies in pharmaceutical services. With features like prescription validation, stock management, secure billing, and auditing, it ensures operational accuracy and compliance.

This project showcases the power of **PL/SQL programming** combined with thoughtful design, making it a practical solution for pharmacy digital transformation.

---

## 🔧 Tools & Technologies Used
- **Database**: Oracle 19c  
- **Language**: PL/SQL  
- **Modeling**: Draw.io, Lucidchart  
- **Monitoring**: Oracle Enterprise Manager  
- **Documentation**: GitHub, PowerPoint  

---

## 📬 Contact
**Muneza Pascal**  
📧 Email: [munezapascal006@gmail.com]  
🔗 GitHub: [Your GitHub Link]  

---

> _"Whatever you do, work at it with all your heart, as working for the Lord, not for human masters."_ — **Colossians 3:23**


