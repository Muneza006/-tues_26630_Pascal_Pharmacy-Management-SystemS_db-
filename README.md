💊 Pharmacy Management System – PL/SQL Oracle Database Project

### 👤 Student Info
- **Name:** Muneza Pascal  
- **Student ID:** 26630  
- **Course:** Database Development with PL/SQL (INSY 8311)  
- **Lecturer:** Eric Maniraguha  
- **Academic Year:** 2024–2025
- 
🧠 Introduction:


Modern pharmacies face increasing challenges due to manual processes that often result in prescription errors, inventory mismatches, delayed patient services, and data inconsistencies. 
To address these pain points, this project introduces a Pharmacy Management System built using Oracle Database and PL/SQL programming. The system provides automation, real-time tracking, and secure data management for prescriptions, inventory, and payments—enhancing service delivery and operational efficiency.

The project was implemented in eight phases, covering everything from problem analysis and business modeling to logical design, implementation, testing, and reporting.

📅 Project Timeline and Structure

Phase | Title
Phase 1 | 🎯 Problem Statement
Phase 2 | 🛠 Business Process Modeling
Phase 3 | 🧩 Logical Model Design
Phase 4 | 🏗️ Physical Database Implementation
Phase 5 | 🧪 Data Insertion
Phase 6 | 🔄 Transaction Handling
Phase 7 | 🔐 Security Features
Phase 8 | 📊 Reporting and Query Optimization

##🎯 Phase 1: Problem Statement

###🧩 Problem Definition

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


## 🛠️ Phase 2: Business Process Modeling (BPM)
### 📌 Objectives
This phase models the end-to-end operations of a pharmacy—from prescription handling to billing. Using BPMN diagrams, the key workflows are broken down for clarity and automation.

### 🧑‍🤝‍🧑 Actors
- **Doctor:** Issues a prescription

- **Patient:** Receives prescription and requests medication

- **Pharmacist:** Reviews prescription and dispenses medicine

- **System:** Manages stock levels, alerts, and payment status

### 🔁 Key Workflows

1. **Prescription Issuance:** Doctor prescribes medicine to patient.

2. **Prescription Validation:** Pharmacist verifies the prescription.

3. **Stock Check:** System checks availability.

4. **Dispensing & Billing:** Medication is issued and payment processed.

5. **Inventory Update:** System updates stock levels automatically.

Maintain secure patient prescription records

Integrate payment management and reporting

## 🧩 Phase 3: Logical Model Design

### 📐 ER Diagram & Entities

The logical model defines the key entities, attributes, and relationships within the system. The main entities include:

- **Patients**: Patient_ID (PK), Name, Contact, Medical_History  
- **Doctors**: Doctor_ID (PK), Name, License, Specialty  
- **Medicines**: Medicine_ID (PK), Name, Stock, Price  
- **Prescriptions**: Prescription_ID (PK), Patient_ID (FK), Doctor_ID (FK), Date  
- **Payments**: Payment_ID (PK), Prescription_ID (FK), Amount, Method  

### 🔗 Relationships

- A doctor can write multiple prescriptions.  
- A patient can receive multiple prescriptions.  
- Each prescription can have one or more medicines.  
- Each prescription corresponds to a payment.  

### ⚙️ Constraints & Normalization

- All entities normalized up to **Third Normal Form (3NF)**  
- Foreign keys and constraints applied to maintain referential integrity  
- Data types and validation rules implemented for reliability



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


