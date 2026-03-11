# Data Dictionary — Hospital Resource Allocation

## Original Columns
| Column | Type | Description |
|---|---|---|
| Patient ID | Text | Unique patient identifier |
| Name | Text | Patient full name |
| Date of Birth | Date | Patient birth date |
| Gender | Text | Male or Female |
| Medical Condition | Text | Primary diagnosis |
| Treatments | Text | Treatment applied |
| Doctor's Notes | Text | Clinical notes from doctor |
| Admit Date | Date | Hospital admission date |
| Discharge Date | Date | Hospital discharge date |
| Bill Amount | Number | Total bill amount in rupees |

## Engineered Columns (created by us)
| Column | Type | Description | How Created |
|---|---|---|---|
| Length of Stay | Number | Days patient was admitted | Discharge Date minus Admit Date |
| Age | Number | Patient age at admission | Admit Date minus Date of Birth |
| Admit Month | Number | Month of admission 1 to 12 | Extracted from Admit Date |
| Admit Day of Week | Number | Day 0 is Monday 6 is Sunday | Extracted from Admit Date |
| Admit Year | Number | Year of admission | Extracted from Admit Date |
| Is Weekend | Binary | 1 if Saturday or Sunday else 0 | From Admit Day of Week |
| Department | Text | Hospital department name | Mapped from Medical Condition |
| Days Since Last Visit | Number | Days since previous admission | Calculated using Patient ID |
| Is Readmission | Binary | 1 if readmitted within 30 days | Days Since Last Visit under 30 |
| Age Group | Category | Child Young Adult Middle Senior Elderly | Created using age ranges |
| Readmission Risk | Binary | Target variable for ML model | Domain driven synthetic flag |