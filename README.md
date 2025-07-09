![Screenshot (322)](https://github.com/user-attachments/assets/3ab17162-de79-4da2-a924-460ed3fc0f7a)
# Massachusetts General Hospital (MGH) Dashboard
This project analyzes patient and hospital operations data from Massachusetts General Hospital using Power BI. It answers key business questions related to patient demographics, encounter patterns, readmission trends, insurance coverage, and cost of care.

# About the Dataset
The dataset contains a year's worth of hospital encounter data, including patient age, gender, encounter class, readmission status, insurance coverage, and cost details. It supports performance monitoring and healthcare service evaluation.

# Key Business Questions Answered
How many patient encounters do we have each month? What’s the readmission trend?
A monthly line chart visualizes total encounters, with a breakdown between first admissions and readmissions to highlight seasonal or operational trends.

What types of encounters are most common?
A bar chart categorizes encounters by class (ambulatory, outpatient, emergency, etc.), revealing how different service types contribute to hospital workload.

What is the age and gender distribution of patients?
Used grouped bar and pie charts to show which age groups (e.g., 65+, 51–65) and genders utilize hospital services most frequently.

How many procedures are covered by insurance?
Displayed total procedures covered and percent covered (e.g., 51.97%) to understand patient coverage levels and insurance penetration.

What is the average cost and length of stay per visit?
Created KPI cards showing:

Average cost per visit: $3.64K

Average length of stay: 7.27 hours

# Data Model Structure
Table Descriptions:
Encounters: Monthly records of each hospital visit, including readmission flags.

Patients: Demographic data such as gender and age.

Procedures: Details on whether procedures were covered by insurance.

Descriptions: Encounter type (ambulatory, inpatient, emergency, etc.)

Relationships:
Procedures[Encounter] → Encounters[Id]

Encounters[PatientId] → Patients[Id]

Encounters[DescriptionId] → Descriptions[Id]

# DAX Measures & Features
Total Encounters: SUM(Encounters[EncounterId])

Percent Procedures Covered: DIVIDE(Covered Procedures, Total Procedures)

Average Cost per Visit: AVERAGEX(Encounters, Encounters[Cost])

Average Length of Stay: AVERAGEX(Encounters, Encounters[LengthOfStay])

Patient Count by Gender: COUNTROWS(DISTINCT(Patients[Id]))

# Dashboard Highlights
Line Chart for encounters by month and readmission status

Bar Charts for:

Encounter class distribution

Patient age group

Pie Chart for gender distribution

KPI Cards for:

Total procedures covered

Total encounters

Patient count

Percent covered

Average cost

Average length of stay

# Tools Used
Power BI Desktop

DAX (Data Analysis Expressions)

Star schema relational modeling

Real-world healthcare operations context

# Business Recommendations
Allocate resources more effectively by monitoring readmission trends.

Invest in insurance outreach to improve procedure coverage rates.

Tailor services to the elderly (65+) who form the largest patient group.

Optimize staff scheduling by identifying peak encounter months.

Use gender and age insights to design personalized patient programs.

# Conclusion
This dashboard empowers MGH’s healthcare administrators and stakeholders to make data-driven decisions that improve patient outcomes, reduce costs, and streamline hospital operations. It transforms raw hospital records into strategic healthcare insights.
