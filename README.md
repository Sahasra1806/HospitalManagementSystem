#  Hospital Management System (Java + MySQL)

A **console-based Hospital Management System** built using **Java** and **JDBC** to manage patients, doctors, and appointments efficiently.  
This system allows hospitals to store patient details, manage doctor availability, and book appointments directly through a command-line interface.

---

##  Features

-  **Add New Patients** — register patient details into the database  
-  **View Patients** — display all registered patients  
-  **View Doctors** — list all doctors from the database  
-  **Book Appointments** — link patients and doctors with an appointment date  
-  **Check Doctor Availability** — ensures doctors are not double-booked  
-  **Persistent Data Storage** — all data stored in a MySQL database  

---

##  Project Overview

The system interacts with a **MySQL database (`hospital`)** and uses **JDBC (Java Database Connectivity)** to execute SQL queries for CRUD operations.

**Main Classes:**
- `HospitalManagementSystem` — main driver class that controls user input and core menu operations  
- `Patient` — handles patient data insertion and retrieval  
- `Doctor` — manages doctor details and listings  

---

##  Tech Stack

| Component | Technology |
|------------|-------------|
| **Programming Language** | Java |
| **Database** | MySQL |
| **Database Connector** | JDBC |
| **IDE** | Eclipse |
| **Driver** | MySQL Connector/J (`com.mysql.cj.jdbc.Driver`) |

---

##  How to Run the Project

### 1️**Set Up the Database**

Open MySQL or MySQL Workbench and run the following commands:

```sql
CREATE DATABASE hospital;
USE hospital;

CREATE TABLE patients (
    patients_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctor (
    doctor_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    specialization VARCHAR(50)
);

CREATE TABLE appointments (
    appointment_id INT PRIMARY KEY AUTO_INCREMENT,
    patients_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patients_id) REFERENCES_
