# Doctors-Performance-and-Patient-Engagement-Analysis-
This repository contains detailed information about the Doctors Performance and Patient Engagement Analysis

# PROJECT TITLE: Doctor Performance and Patient Engagemnt Analysis


[Introduction](Introduction)

[Data Description](Data-Description)

[Methodology](Methodology)

[Queries](Queries)

[Visualizations](Visualizations)

[Findings](Findings)

[Recommendations](Recommendations)


## INTRODUCTION
Healthcare facilities are constantly striving to improve efficiency and patient care. One key aspect of this is understanding doctor performance and workload. This analysis looks at data from patients, doctors, appointments, and medical procedures to gain insights into how doctors manage their time, how efficiently appointments are managed, and what factors impact patient satisfaction.

By analyzing this data, we can identify trends in workload distribution, appointment delays, and the demand for different medical procedures. These insights can help hospitals and clinics allocate resources better, streamline operations, and enhance the quality-of-care patients receive.

### Objectives

1.	To assess doctors’ workload 
2.	To identify specialization trends
3.	To ascertain common medical procedures per specialization 
4.	To analyze procedure demand 
5.	To assess patient engagement & frequency 

Research questions
•	How does the number of appointments vary among doctors, and what patterns can be observed in workload distribution?
•	Which medical specializations handle the highest number of unique patients and procedures?
•	Which medical procedures are most frequently performed within each specialization?
•	Which medical procedures are in the highest demand, and which doctors perform them most frequently?
•	Which patients have the highest number of visits, and what factors influence their engagement levels?
DATA DESCRIPTION 
Four tables will be used for this analysis. The patient table stores information about individual patients, including their names and contact details. The doctors table contains details about healthcare providers, including their names, specializations, and contact information. The appointment table records scheduled appointments, linking patients to doctors. The medical procedure table stores details about medical procedures associated with specific appointments.

Key Features
Patients Table:
•	PatientID: Unique identifier for each patient.
•	PatientName: First name of the patient.
•	Email: Email address of the patient.

Doctors Table:
•	DoctorID: Unique identifier for each doctor.
•	DoctorName: Full name of the doctor.
•	Specialization: Area of medical specialization.
•	DoctorContact: Contact details of the doctor.


Appointments Table:
•	AppointmentID: Unique identifier for each appointment.
•	Date: Date of the appointment.
•	Time: Time of the appointment.
•	PatientID: Foreign key referencing the Patients table, indicating the patient for the appointment.
•	DoctorID: Foreign key referencing the Doctors table, indicating the doctor for the appointment.

Medical Procedure Table:
•	ProcedureID: Unique identifier for each medical procedure.
•	ProcedureName: Name or description of the medical procedure.
•	AppointmentID: Foreign key referencing the Appointments table, indicating the appointment associated with the procedure.


METHODOLOGY
The data was retrieved from a structured SQL database, and joins were performed to establish relationships between tables. 
Data Cleaning
•	Missing values: Tables were checked for missing values, and none were found.
•	Inconsistencies: Columns with inconsistent case format were uniformed. The ‘Datetime’ column was converted to ‘hh: mm: ss’ data type
•	Merged Columns: In doctors table, ‘Firstname’ column was merged with ‘Email’ column to create a proper email address. The ‘Firstname’ column was merged with the ‘Lastname’ column to create ‘PatientName’ column.

Data Analysis
1.	To assess doctors’ workload 
•	Doctors were categorized into workload levels using a CASE statement.
•	Identified potential underutilized and overworked doctors.

2.	To identify specialization trends
•	A CTE (Specialization_summary) was created to analyze patient volume per specialization.
•	A CASE statement was used to classify specializations based on patient volume.

3.	To ascertain common medical procedures per specialization 
•	ROW_NUMBER () was used to determine the most performed procedure per specialization.
•	The query helps in resource allocation and specialization-based insights. 

4.	To analyze procedure demand 
•	A CTE (Procedure_summary) calculated the total procedures per doctor.
•	A CASE statement classified procedures into High, Moderate, and Low Demand.

5.	To assess patient engagement & frequency 
•	A subquery counted the total visits per patient.
•	A CASE statement classified patients into:
	Frequent Visitors (≥ 4 visits)
	Occasional Visitors (1–3 visits)
	Non-Visitors (0 visits)
Data Analysis and Interpretation
After executing the queries, the results were analyzed to extract patterns:
1.	Workload distribution among doctors helped in identifying overburdened and underutilized medical staff.
2.	Specialization trends revealed which fields handle the most patients and procedures.
3.	Procedure frequency analysis provided insights into hospital resource planning and demand forecasting.
4.	Patient engagement tracking identified individuals with frequent hospital visits, allowing for targeted patient follow-ups.

FINDINGS
1.	Workload distribution among doctors
20 doctors have a High Workload, 43 doctors have a Moderate Workload, 317 doctors have a Low Workload, and 120 doctors have No Workload.
2.	Specialization trends
66.67% of specializations have High Patient Volume and the remaining 33.33% have a Low Patient Volume 
3.	Procedure frequency analysis

Comprehensive geriatric assessment procedure has the highest demand in the High Demand Category.

Allergy testing procedure has the highest demand in the Moderate Demand Category.

Advanced cardiac life support procedure has the highest demand in the Low Demand Category.

4.	Patient engagement tracking

65.06% of the patients visit Occasionally, 32.28% of the patients have No visits and 2.66% of the patients visit Frequently.

The findings were visualized using Power BI for better interpretation.


RECOMMENDATIONS
1.	Workload Distribution: Redistribute patient appointments to balance doctors' workloads and prevent burnout, using a dynamic scheduling system for real-time adjustments.
2.	Specialization Trends: Support high-demand specializations by hiring more staff or improving patient management. For low-demand specializations, consider marketing or consolidating specialties.
3.	Procedure Frequency: Prioritize high-demand procedures (like geriatric assessments) by ensuring adequate resources and forming dedicated teams for these procedures.
4.	Patient Engagement: Increase visit frequency by encouraging regular check-ups through outreach programs, reminders, and education. Investigate low engagement for patients with no visits and find ways to improve accessibility or appeal.

