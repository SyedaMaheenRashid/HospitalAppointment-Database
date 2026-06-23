# 🏥 Hospital Appointment Management System (MongoDB)

## 📖 Introduction

The Hospital Appointment Management System is a NoSQL database project developed using MongoDB. This project simulates a hospital management environment where patient records, doctor details, appointment scheduling, and admin management are handled efficiently through a document-based database system.

This project is designed for students, beginners, and database learners who want to understand MongoDB database design through a real-world healthcare application. It demonstrates proper collection design, CRUD operations, relationships between entities, query handling, and report generation.

---

## 🎯 Project Objectives

The main objectives of this project are:

* Design a complete hospital appointment database using MongoDB
* Implement a real-world NoSQL database structure
* Store and manage patient, doctor, appointment, and admin information
* Perform CRUD operations on hospital data
* Generate useful hospital-related reports
* Practice MongoDB queries and aggregation pipelines
* Understand document-based database architecture
* Develop hands-on experience with MongoDB Compass and Mongo Shell

---

## 🌟 Features

* ✅ Complete MongoDB Database Project
* ✅ 4 Interconnected Collections
* ✅ Realistic Hospital Data
* ✅ Patient Management
* ✅ Doctor Management
* ✅ Appointment Scheduling
* ✅ Admin Record Management
* ✅ MongoDB Query Practice
* ✅ Aggregation Pipelines
* ✅ Report Generation
* ✅ MongoDB Compass Compatible
* ✅ Beginner-Friendly Structure

---

## 🏗 System Overview

The Hospital Appointment System consists of four major entities:

### 👤 Patients

Stores patient details such as name, age, gender, contact, and disease.

### 🩺 Doctors

Stores doctor details such as name, specialization, department, and availability.

### 📅 Appointments

Stores appointment records by linking patients with doctors along with date, time, and status.

### 🔐 Admins

Stores admin information responsible for managing the hospital database system.

---

## 🗂 Database Collections

## 1️⃣ Patients Collection

Stores patient information.

### Sample Document

```json
{
  "_id": ObjectId(),
  "name": "Ali Raza",
  "age": 24,
  "gender": "Male",
  "phone": "03001234567",
  "address": "Lahore",
  "disease": "Fever"
}
```

### Fields

| Field   | Description             |
| ------- | ----------------------- |
| _id     | Unique Patient ID       |
| name    | Patient Name            |
| age     | Patient Age             |
| gender  | Patient Gender          |
| phone   | Contact Number          |
| address | Patient Address         |
| disease | Patient Disease/Problem |

---

## 2️⃣ Doctors Collection

Stores doctor information.

### Sample Document

```json
{
  "_id": ObjectId(),
  "name": "Dr. Sara Ahmed",
  "specialization": "Cardiologist",
  "department": "Cardiology",
  "phone": "03111222333",
  "availability": "Mon-Fri"
}
```

### Fields

| Field          | Description           |
| -------------- | --------------------- |
| _id            | Unique Doctor ID      |
| name           | Doctor Name           |
| specialization | Doctor Specialization |
| department     | Department Name       |
| phone          | Contact Number        |
| availability   | Available Days        |

---

## 3️⃣ Appointments Collection

Stores appointment records.

### Sample Document

```json
{
  "_id": ObjectId(),
  "patient_name": "Ali Raza",
  "doctor_name": "Dr. Sara Ahmed",
  "appointment_date": "2026-06-20",
  "appointment_time": "11:00 AM",
  "status": "Confirmed"
}
```

### Fields

| Field            | Description           |
| ---------------- | --------------------- |
| _id              | Unique Appointment ID |
| patient_name     | Patient Name          |
| doctor_name      | Doctor Name           |
| appointment_date | Appointment Date      |
| appointment_time | Appointment Time      |
| status           | Appointment Status    |

---

## 4️⃣ Admins Collection

Stores admin information.

### Sample Document

```json
{
  "_id": ObjectId(),
  "name": "Admin User",
  "email": "admin@hospital.com",
  "password": "admin123"
}
```

### Fields

| Field    | Description     |
| -------- | --------------- |
| _id      | Unique Admin ID |
| name     | Admin Name      |
| email    | Admin Email     |
| password | Admin Password  |

---

## 🔗 Database Relationships

PATIENTS
│
▼
APPOINTMENTS
▲
│
DOCTORS

ADMINS
│
▼
SYSTEM MANAGEMENT

### Relationship Summary

| Relationship              | Type                        |
| ------------------------- | --------------------------- |
| Patient → Appointments    | One-to-Many                 |
| Doctor → Appointments     | One-to-Many                 |
| Admin → System Management | One-to-One / Administrative |

---

## 📊 Database Statistics

| Collection   | Documents |
| ------------ | --------- |
| Patients     | 10        |
| Doctors      | 8         |
| Appointments | 12        |
| Admins       | 2         |

### Additional Insights

* Total Patients Registered: 10+
* Total Doctors Available: 8
* Confirmed Appointments: 7
* Pending Appointments: 3
* Cancelled Appointments: 2
* Multiple hospital departments covered
* Realistic hospital database design for learning

---

## 📁 Project Structure

```bash
HospitalAppointment-Database/
│
├── README.md
├── LICENSE
│
├── data/
│   ├── patients.json
│   ├── doctors.json
│   ├── appointments.json
│   └── admins.json
│
├── queries/
│   ├── find_queries.txt
│   ├── update_queries.txt
│   ├── delete_queries.txt
│   └── aggregate_queries.txt
│
├── reports/
│   ├── patient_report.txt
│   ├── doctor_report.txt
│   ├── appointment_report.txt
│   └── admin_report.txt
│
├── documentation/
│   └── project_documentation.pdf
│
└── screenshots/
```

---

## 🚀 Installation Guide

### Step 1: Install MongoDB

Download MongoDB Community Server from the official website.

### Step 2: Install MongoDB Compass

Download and install MongoDB Compass for managing collections visually.

### Step 3: Connect to MongoDB

Use the following connection string:

```bash
mongodb://localhost:27017
```

### Step 4: Create Database

```js
use HospitalAppointmentDB
```

### Step 5: Create Collections

Create the following collections:

* patients
* doctors
* appointments
* admins

### Step 6: Import JSON Files

Using MongoDB Compass:

* Open the database
* Create collection
* Click **Add Data**
* Select **Import JSON**
* Choose the relevant file
* Import data for each collection

---

## 🔍 Sample Queries

### Find All Patients

```js
db.patients.find()
```

### Find Female Patients

```js
db.patients.find({ gender: "Female" })
```

### Find Doctors in Cardiology Department

```js
db.doctors.find({ department: "Cardiology" })
```

### Find Confirmed Appointments

```js
db.appointments.find({ status: "Confirmed" })
```

### Find Admin by Email

```js
db.admins.find({ email: "admin@hospital.com" })
```

---

## 📈 Aggregation Queries

### Count Patients by Gender

```js
db.patients.aggregate([
  {
    $group: {
      _id: "$gender",
      totalPatients: { $sum: 1 }
    }
  }
])
```

### Count Doctors by Department

```js
db.doctors.aggregate([
  {
    $group: {
      _id: "$department",
      totalDoctors: { $sum: 1 }
    }
  }
])
```

### Count Appointments by Status

```js
db.appointments.aggregate([
  {
    $group: {
      _id: "$status",
      totalAppointments: { $sum: 1 }
    }
  }
])
```

---

## 🎓 Learning Outcomes

This project demonstrates:

* MongoDB Fundamentals
* NoSQL Database Design
* Collections and Documents
* CRUD Operations
* Aggregation Pipelines
* Data Modeling
* Database Relationships
* Report Generation
* MongoDB Compass Usage
* Real-World Database Development

---

## 💼 Portfolio Benefits

This project can be used for:

* University Database Projects
* Advanced Database Lab Submission
* MongoDB Practice
* GitHub Portfolio
* Internship Applications
* Entry-Level Developer Portfolio
* Database Administrator Learning
* NoSQL Development Practice

---

## 🛠 Technologies Used

* MongoDB
* MongoDB Compass
* JSON
* Mongo Shell Queries
* NoSQL Database Architecture

---

## 🤝 Contribution

Contributions are welcome.

* Fork the repository
* Create a new branch
* Commit your changes
* Push to your branch
* Open a Pull Request

---

## 📜 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Maheen Rashid**
BSCS Student
MongoDB Database Project

---

## ⭐ Support

If you found this project useful:

* ⭐ Star the repository
* 🍴 Fork the repository
* 📢 Share it with others
* 💡 Suggest improvements
