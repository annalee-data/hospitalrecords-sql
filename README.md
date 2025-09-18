# Hospital Records Analysis (SQL)
*Hospital Patient & Doctors Analysis using Oracle SQL Developer*

Analyzed hospital reports for answering business questions using SQL.
<br>

## 1. Business Scenario
You are working for a mid-sized hospital. Management wants to understand patient outcomes, doctor performance, and prescription patterns from the records between the dates 01/01/2021 to 12/31/2023. You are authorized to these hospital records, use SQL to answer management's questions.

⭐️ Goal: Create SQL queries to answer the following questions.
1. What is the average hospital stay by condition?
2. What is the patient discharge rate?
3. What is the most prescribed medication?
4. Which doctors handle the most appointments?
5. How does the doctor performance look like with patient outcomes?

<br>

## 2. Dataset
There are a total of 4 CSV files used for this project. These datasets were created by Mockaroo, a random data generator.
### 1. [patients.csv](patients.csv) 
| Variable Name | Type | Description |
| :------- | :------: | :------ |
| patient_id  | INTEGER (PK)  | Unique ID  |
| first_name  | TEXT  | Patient's first name  |
| last_name  | TEXT  | Patient's last name  |
| gender  | TEXT  | M/F  |
| dob  | DATE  | Date of birth (MM/DD/YYYY), 01/01/1940-12/31/2015  |
| admission_date  | DATE  | Date admitted (MM/DD/YYYY), 01/01/2021-12/31/2023  |
| condition  | TEXT  | Condition (e.g., "arthritis", "diabetes")  |
| discharged  | BOOLEAN  | "true", "false"  |

total of 200 rows.
### 2. [doctors.csv](doctors.csv)
| Variable Name | Type | Description |
| :------- | :------: | :------ |
| doctor_id  | INTEGER (PK)  | Unique ID  |
| first_name  | TEXT  | Patient's first name  |
| last_name  | TEXT  | Patient's last name  |
| specialty  | TEXT  | Specialty type (e.g., "Psychiatry", "Surgery")  |
| experience  | INTEGER  | Years of experience  |

total of 25 rows
### 3. [appointments.csv](appointments.csv)
| Variable Name | Type | Description |
| :------- | :------: | :------ |
| appointment_id  | INTEGER (PK)  | Unique ID  |
| patient_id  | INTEGER (FK)  | patient_id from patients dataset  |
| doctor_id  | INTEGER (FK)  | doctor_id from doctors dataset  |
| appointment_date  | DATE  | Date of appointment (MM/DD/YYYY), 01/01/2021-12/31/2023 |
| treatment  | TEXT  | Treatment type (e.g., "acupuncture", "chiropractric")  |
| outcome  | BOOLEAN  | "Improved", "No Change", "Worsened"  |

total of 500 rows
### 4. [prescriptions]()
| Variable Name | Type | Description |
| :------- | :------: | :------ |
| prescription_id  | INTEGER (PK)  | Unique ID  |
| patient_id  | INTEGER (FK)  | patient_id from patients dataset  |
| doctor_id  | INTEGER (FK)  | doctor_id from doctors dataset  |
| medication_name  | TEXT  | Medication name (e.g., "Simvastatin", "Omeprazole"  |
| dosage  | BOOLEAN  | Dosage type (e.g., "50mg", "110mg")  |

total of 300 rows


