# Electronic Medical Record (EMR) System

An Electronic Medical Record (EMR) system is a digital version of a patient's paper chart used within a single healthcare organization (such as a clinic or hospital). It stores and manages patient health information electronically to improve the quality, efficiency, and safety of healthcare.

This repository contains the database design for the project as well as a full-stack (React + Node.js + MySQL) implementation with role-based dashboards for administrators, receptionists, and physicians.

## Repository Structure

```
Electronic-Medical-Record-System/
├── sql files/                          # Standalone SQL scripts (schema, queries, views, procedures, triggers)
├── healthcare-emr-system-main/         # Full-stack web application (React frontend + Express/MySQL backend)
├── ER_Diagram.jpeg                     # Entity-Relationship diagram
├── UML_Diagram.jpeg                    # UML diagram
├── PROJECT REPORT.pdf                  # Written project report
├── EMR_Project2_Presentation.pptx      # Project presentation slides
└── final_project_presentation.mp4      # Recorded project presentation
```

## Database (`sql files/`)

Core MySQL scripts covering the full data model:

- `create.sql` – table definitions (Patient, Doctor, Appointment, Prescription, Medication, User, Role, Permission, Audit_Log, Patient_History, Prescription_History, etc.)
- `insert.sql` – sample data
- `simple_Queries.sql`, `complex_Queries.sql`, `Basic_information_obtained.sql`, `More_Insightful_information_queries.sql` – example queries
- `views.sql` – database views (e.g. user permissions view)
- `stored_procedures.sql` – stored procedures
- `triggers.sql` – audit/history triggers
- `index.sql` – indexes for performance

Diagrams for the schema are available in [ER_Diagram.jpeg](ER_Diagram.jpeg) and [UML_Diagram.jpeg](UML_Diagram.jpeg), with full design rationale in [PROJECT REPORT.pdf](PROJECT%20REPORT.pdf).

## Web Application (`healthcare-emr-system-main/`)

A complete EMR web app with role-based access control.

### Features

- **Administrator** – audit log dashboard with filtering by table, operation type, and date; view old/new value change history
- **Receptionist** – patient CRUD and search, appointment scheduling and management
- **Physician** – view assigned appointments, create/manage prescriptions, view medication database

### Tech Stack

| Layer    | Technology |
|----------|------------|
| Frontend | React 19, React Router DOM, Axios, react-select |
| Backend  | Node.js, Express.js |
| Database | MySQL 8.0 (mysql2 client), views, stored procedures, triggers, audit logging |

### Prerequisites

- Node.js v14+
- MySQL 8.0+
- npm or yarn

### Setup

**1. Database**

Run the SQL scripts in `healthcare-emr-system-main/healthcare-emr-system-main/backend/sql_files/`:
- `project1/` – basic schema and sample data
- `project2/` – advanced schema with views, stored procedures, triggers, and indexes (run in order)

**2. Backend**

```bash
cd healthcare-emr-system-main/healthcare-emr-system-main/backend
npm install
cp .env.example .env   # then fill in DB_HOST, DB_PORT, DB_USER, DB_PASSWORD, DB_NAME
npm start
```

Runs on `http://localhost:8000`.

**3. Frontend**

```bash
cd healthcare-emr-system-main/healthcare-emr-system-main/frontend
npm install
cp .env.example .env   # REACT_APP_API_URL=http://localhost:8000/api for local dev
npm start
```

Runs on `http://localhost:3000`.

See [healthcare-emr-system-main/healthcare-emr-system-main/README.md](healthcare-emr-system-main/healthcare-emr-system-main/README.md) for full application documentation, including the backend route layout, frontend structure, and database schema reference.

## Project Materials

- [ER Diagram](ER_Diagram.jpeg)
- [UML Diagram](UML_Diagram.jpeg)
- [Project Report](PROJECT%20REPORT.pdf)
- [Presentation Slides](EMR_Project2_Presentation.pptx)
- [Presentation Recording](final_project_presentation.mp4)
