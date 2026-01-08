# Schema Design

## MySQL Database Design

### Patient

- id BIGINT, PRIMARY KEY, AUTO INCREMENT
- name VARCHAR, NOT NULL
- email VARCHAR, NOT NULL
- password VARCHAR, NOT NULL
- contact VARCHAR, NOT NULL
- created_at TIMESTAMP, NOT NULL
- updated_at TIMESTAMP, NOT NULL
- 
### Doctor

- id BIGINT, PRIMARY KEY, AUTO INCREMENT
- name VARCHAR, NOT NULL
- username VARCHAR, NOT NULL
- password VARCHAR, NOT NULL
- contact VARCHAR, NOT NULL
- created_at TIMESTAMP, NOT NULL
- updated_at TIMESTAMP, NOT NULL

### Appointments

- id BIGINT, PRIMARY KEY, AUTO INCREMENT
- doctor_id BIGINT, FOREIGN KEY (doctor.id)
- patient_id BIGINT, FOREIGN KEY (patient.id)
- appointment_time: TIMESTAMP, NOT NULL
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)
- created_at TIMESTAMP, NOT NULL
- updated_at TIMESTAMP, NOT NULL

### Admin

- id BIGINT, PRIMARY KEY, AUTO INCREMENT
- name VARCHAR, NOT NULL
- username VARCHAR, NOT NULL
- password VARCHAR, NOT NULL
- created_at TIMESTAMP, NOT NULL
- updated_at TIMESTAMP, NOT NULL
  
### Payments

- id BIGINT, PRIMARY KEY, AUTO INCREMENT
- appointment_id BIGINT, FOREIGN KEY (appointment.id)
- status: INT (0 = Waiting, 1 = Executed, 2 = Cancelled)
- created_at TIMESTAMP, NOT NULL
- updated_at TIMESTAMP, NOT NULL

## MongoDB Collection Design

### Prescriptions
```json
{
  "id": "ObjectId('64abc123456')",
  "patientName": "John Smith",
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
