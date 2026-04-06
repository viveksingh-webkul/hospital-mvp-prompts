System Name: Hospital Management System (MVP)

Objective:
Build a minimal hospital management system covering OPD (outpatient) and IPD (inpatient) workflows.

User Roles:
- Admin
- Receptionist
- Doctor

Core Modules:
- Patient Management
- Doctor Management
- Appointment (OPD)
- Consultation & Prescription
- IPD Admission & Discharge

--------------------------------------------------

1. Patient Management

Entity: Patient

Fields:
- patient_id (auto-generated, unique)
- name (string, required)
- age (integer, required)
- gender (selection)
- mobile (unique, required)
- address (text)

--------------------------------------------------

2. Doctor Management

Entity: Doctor

Fields:
- doctor_id (auto-generated)
- name (required)
- specialization
- consultation_fee
- available_days
- available_time

--------------------------------------------------

3. Appointment Management (OPD)

Entity: Appointment

Fields:
- appointment_id
- patient_id (relation)
- doctor_id (relation)
- appointment_date
- appointment_time
- status (scheduled/completed/cancelled)

Workflow:
1. Receptionist books appointment
2. Select patient & doctor
3. Select date/time
4. Validate availability
5. Create appointment

Rules:
- No double booking

--------------------------------------------------

4. Consultation & Prescription

Entities:
- Consultation
- Prescription

Consultation Fields:
- consultation_id
- patient_id
- doctor_id
- appointment_id
- notes

Prescription Fields:
- medicine_name
- dosage
- duration

Workflow:
1. Doctor opens appointment
2. Adds diagnosis
3. Adds medicines
4. Saves consultation

--------------------------------------------------

5. IPD Management

Entity: Admission

Fields:
- admission_id
- patient_id
- doctor_id
- admission_date
- bed_number
- status (admitted/discharged)
- discharge_date

Workflow:

Admission:
1. Select patient
2. Assign doctor
3. Assign bed
4. Validate bed availability
5. Create admission

During Stay:
- Doctor can view admitted patients
- Add notes

Discharge:
1. Open admission
2. Click discharge
3. Update status

Rules:
- One bed = one active patient
- Cannot discharge twice

--------------------------------------------------

Global Business Rules:
- All IDs must be unique
- Mandatory fields validation
- Relationships must be enforced

--------------------------------------------------

API Requirements:
- /patients
- /doctors
- /appointments
- /consultations
- /admissions

--------------------------------------------------

UI Requirements:
- Dashboard (basic counts)
- List + Form views for all modules
- Search & filter options

--------------------------------------------------

Expected Output:
- Fully functional MVP hospital system
- Supports OPD + IPD basic workflows

