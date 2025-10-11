# CareSync


## Overview
The CareSync-Hospital Management System (HMS) is an Oracle database-driven application with Java front-end (Java Swing/Frames). It manages patients, staff, rooms, treatments, and billing efficiently. The system also implements PL/SQL procedures for common operations and audit triggers for tracking database changes.

## Features
- Patient management (Add, Update, Delete)
- Room management
- Staff management
- Treatment records
- Billing generation
- Audit logging for key operations
- PL/SQL procedures for:
  - Adding new patients
  - Recording treatments done by staff
  - Generating bills automatically

## Database Schema

### Tables
- **PATIENT**: Stores patient information (`P_ID`, `P_NAME`, `GENDER`, `CONTACT`, `ADDRESS`, `DOB`, `DOA`, `DOD`)  
- **STAFF**: Stores staff information (`S_ID`, `NAME`, `GENDER`, `JOB`, `DOB`, `CONTACT`, `ADDRESS`)  
- **ROOM**: Stores room information (`ROOM_NO`, `TYPE`, `RENT`)  
- **TREATMENTS**: Stores treatment information (`T_ID`, `T_NAME`, `COST`)  
- **DONE_BY**: Records treatments done by staff (`T_NO`, `P_ID`, `T_ID`, `S_ID`, `T_DATE`, `REMARKS`)  
- **TREATED_IN**: Tracks patient room stays (`P_ID`, `ROOM_NO`, `NO_OF_DAYS`, `IN_DATE`)  
- **BILL**: Stores patient billing details (`BILL_ID`, `ROOM_COST`, `TREATMENT_COST`, `OTHER_COST`)  

### Audit Tables
- **PATIENT_AUDIT**  
- **BILL_AUDIT**  
- **DONE_BY_AUDIT**  
- **TREATED_IN_AUDIT**  

Audit tables automatically log `INSERT`, `UPDATE`, and `DELETE` operations on corresponding tables.

## PL/SQL Procedures
- `ADD_PATIENT`: Adds a new patient to the database  
- `ADD_DONE_BY`: Records a treatment done by staff  
- `GENERATE_BILL`: Calculates and inserts a patient bill based on treatments and room usage  

## Triggers
- `PATIENT_AUDIT_TRG`  
- `BILL_AUDIT_TRG`  
- `DONE_BY_AUDIT_TRG`  
- `TREATED_IN_AUDIT_TRG`  

Triggers automatically maintain audit logs for all key operations in the system.

## Installation

### Requirements
- Oracle Database
- SQL Developer or SQL*Plus
- Java JDK (for front-end)
- NetBeans IDE (if using Java Swing front-end)

### Screenshots
<img width="931" height="596" alt="Screenshot 2025-10-11 173758" src="https://github.com/user-attachments/assets/7e741e55-0440-4320-9f30-5a36b69fd9be" />
<img width="944" height="615" alt="image" src="https://github.com/user-attachments/assets/3780f296-e602-4c02-83af-1b9bc42b213f" />
<img width="1108" height="685" alt="image" src="https://github.com/user-attachments/assets/cddff4da-4c85-40b6-acf1-d8cfa144a476" />
<img width="1006" height="713" alt="image" src="https://github.com/user-attachments/assets/ef3801b4-07aa-479e-94a7-2dcfce54c975" />
<img width="1101" height="657" alt="image" src="https://github.com/user-attachments/assets/fdcf2804-3404-4a8a-ad56-f2ba48af489c" />





