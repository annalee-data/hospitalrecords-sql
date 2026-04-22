# Hospital Records Analysis (SQL)
*Hospital Patient & Doctors Analysis using Oracle SQL Developer*

Analyzed hospital reports for answering business questions using SQL.
<br>

## Business Scenario
Management wants to understand patient outcomes, doctor performance, and prescription patterns from the records between the dates 01/01/2021 to 12/31/2023. You are authorized to these hospital records, use SQL to answer management's questions.

⭐️ Goal: Create SQL queries to answer the following questions.
1. What is the total patients by condition?
2. What is the most prescribed medication?
3. Which doctors handle the most appointments?
4. What is the patient discharge rate?
5. How does the doctor performance look like with patient outcomes?

<br>

## Datasets
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
### 4. [prescriptions](prescriptions.csv)
| Variable Name | Type | Description |
| :------- | :------: | :------ |
| prescription_id  | INTEGER (PK)  | Unique ID  |
| patient_id  | INTEGER (FK)  | patient_id from patients dataset  |
| doctor_id  | INTEGER (FK)  | doctor_id from doctors dataset  |
| medication_name  | TEXT  | Medication name (e.g., "Simvastatin", "Omeprazole")  |
| dosage  | BOOLEAN  | Dosage type (e.g., "50mg", "110mg")  |

total of 300 rows

<br>

## ERD (Entity-Relationship Diagram)
Using data dictionary on Oracel SQL Developer, I created an ERD.

<img width="844" height="623" alt="Screenshot 2025-09-19 at 9 42 56 PM" src="https://github.com/user-attachments/assets/956d0cab-e204-4925-9711-52a32a7ed3e3" />

*pdf file [here](HospitalERD.pdf)*

<br>

## Assigning PK and FK
Due to creating the datasets separately through a random data generator, I had to query to manually create relationships using FOREIGN KEY and PRIMARY KEY.

<img width="408" height="382" alt="Screenshot 2025-09-19 at 9 44 34 PM" src="https://github.com/user-attachments/assets/58343a7e-afe6-4c95-a7b3-f4d8c28fbbde" />


<br>
<br>

EXPLANATION
- **ALTER TABLE** table_name: used to modify the structure of an existing table.
- **ADD CONSTRAINT** constraint_name <ins>type of rule</ins> column_name: used to define a new rule for an existing column.

    <ins>type of rule</ins> used:
    - PRIMARY KEY: uniquely identifies each row
    - FOREIGN KEY: creates a link between two tables
- **FOREIGN KEY** column_name **REFERENCES** pk_table_name (pk_column_name): creates a link between column_name in the desired foregin key to reference the pk_column_name in pk_table_name.

<br>

SQL file with queries, attached [here](portfolio.sql).




## Key Findings

**1. Patients by Condition**
Arthritis had the highest patient count at 25, followed closely by obesity and hypertension at 24 each. Diabetes and asthma had the lowest counts at 20 patients each.

**2. Most Prescribed Medication**
Simvastatin was the most prescribed medication with 69 prescriptions, followed by Lisinopril (63) and Omeprazole (61). Notably, all top 3 medications are commonly associated with chronic condition management — consistent with arthritis, hypertension, and heart disease being among the top patient conditions.

**3. Busiest Doctors by Appointments**
Dr. Joseito Cuniffe handled the most appointments at 27, followed by Dr. Ulrick Boncore and Dr. Rosalie Piesing at 25 each.

**4. Patient Discharge Rate**
47% of patients were successfully discharged during the 2021–2023 period.

**5. Doctor Performance vs. Patient Outcomes**
Dr. Gene Scotter had the highest patient improvement rate at 57.14% despite not being the busiest doctor — suggesting appointment volume alone doesn't determine outcome quality. Interestingly, Dr. Ulrick Boncore had one of the highest appointment counts (25) but one of the lowest improvement rates (24%), which may warrant further investigation.

### Back to Portfolio Hub click [here](https://github.com/annalee-data/portfolio/blob/main/README.md)
