# Hospital Performance Analysis

A healthcare analytics project analysing 5,000 hospital patient encounters 
to identify operational performance patterns, clinical outcomes, and 
financial trends. Built as part of the Dataverse Healthcare Analytics 
Internship Program.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Data Analysis](#data-analysis)
- [Results](#resultsfindings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)

---

## Project Overview
This project simulates a real-world hospital analytics assignment. 
Acting as a Junior Healthcare Data Analyst, the objective was to:
- Identify 10 meaningful operational and clinical performance metrics
- Clean and prepare a raw hospital encounter dataset
- Build a 3-page interactive Power BI dashboard for hospital leadership
- Deliver a narrative insight report interpreting the findings

The analysis answers three core leadership questions:
- How is this hospital performing operationally?
- Where are the risks and pressure points?
- What should leadership pay attention to first?

---

## Data Sources
- **Dataset:** Hospital Encounter Dataset
- **Records:** 5,000 patient encounters
- **Period:** January 2025
- **Columns:** 17 original fields covering patient demographics, 
  clinical coding, operational timestamps, financial data, and outcomes

---

## Tools
- **Microsoft Excel** — Metric calculation and data cleaning
- **Power Query** — Date formatting and data transformation
- **Power BI** — Interactive dashboard and data visualisation
- **DAX** — Custom measures and calculated columns
- **Microsoft Word** — Project documentation and reporting

---

## Data Cleaning
The raw dataset contained multiple quality issues that were identified 
and resolved before analysis:

| Issue | Action Taken |
|-------|-------------|
| Inconsistent readmission flag | Rebuilt using 30-day rule with MAXIFS |
| Disposition/outcome contradictions | Resolved using IF logic — outcome takes precedence |
| Emergency + Elective contradictions | Reclassified 286 records to Emergency |
| Pediatrics age misclassification | 463 adult patients labelled as Misclassified |
| 120 null cost values | Replaced with median cost by department and severity |
| Multiple ages per patient | Median age per patient applied |
| Multiple genders per patient | Most frequent gender per patient applied |
| ICD-10 codes — no plain language | Mapped to diagnosis names via VLOOKUP |
| CPT codes — no plain language | Mapped to procedure names via VLOOKUP |

**Clean columns created:**
`clean_disposition` | `clean_admission_type` | `clean_department` | 
`clean_cost` | `clean_age` | `clean_gender` | `new_readmission_flag` | 
`diagnosis_name` | `procedure_name`

---

## Data Analysis
**Week 1 — Metrics Identification**

Ten performance metrics were identified and calculated from the raw dataset:

| # | Metric | Value |
|---|--------|-------|
| 1 | Average Length of Stay | 2.59 days |
| 2 | Average ED Wait Time | 46.9 minutes |
| 3 | Patient Recovery Rate | 94.2% |
| 4 | Average Cost Per Encounter | $1,642 |
| 5 | Emergency Admission Rate | 66.08% |
| 6 | High Severity Case Rate | 34.7% |
| 7 | Home Discharge Rate | 79.4% |
| 8 | Cost-to-Severity Gradient | $863 → $2,377 |
| 9 | 30-Day Readmission Rate | 61.4% |
| 10 | Non-Home Discharge Rate | 20.2% |

**Week 3 — Dashboard**

A 4-page Power BI dashboard was built covering:
- **Page 1:** Operational Overview
- **Page 2:** Clinical Performance
- **Page 3:** Financial Analysis
- **Page 4:** Narrative Insight Report

---

## Dashboard Preview

### Page 1 — Operational Overview
<img width="2425" height="1354" alt="Operational Overview" src="https://github.com/user-attachments/assets/7122c029-f1c9-49d1-bce8-fb122fb1b560" />


### Page 2 — Clinical Performance
![Clinical Performance](your-image-link-here)

### Page 3 — Financial Analysis
![Financial Analysis](your-image-link-here)

## Results/Findings
1. The hospital demonstrates strong clinical effectiveness with a 
   **94.2% recovery rate** and lean average LOS of **2.59 days** 
   despite 34.7% high-severity cases
2. **66.08% emergency admissions** signals a predominantly reactive 
   care environment limiting capacity planning
3. **Internal Medicine** consistently leads across severity burden, 
   LOS, and cost — the highest pressure department
4. The **cost-to-severity gradient** rises cleanly from $863 to $2,377 
   confirming coding integrity and resource alignment
5. Top diagnoses — UTI, Hypertension, Type 2 Diabetes — reflect a 
   high burden of chronic preventable conditions

---

## Recommendations
1. Establish contingency staffing protocols to manage unplanned 
   emergency demand more effectively
2. Review discharge planning processes to address the 61.4% 
   readmission flag rate
3. Investigate Pediatrics cost drivers — disproportionately high cost 
   relative to severity profile
4. Explore community health partnerships to reduce chronic 
   disease-driven emergency admissions
5. Conduct peak-hour ED wait time analysis to identify and address 
   dangerous spikes masked by averages

---

## Limitations
- 26 patients had no gender data available across all encounters
- The 61.4% readmission flag reflects the 30-day rule applied across 
  all encounters — definition should be validated with clinical 
  leadership before external reporting
- 463 adult patients in Pediatrics were labelled Misclassified — 
  true department unknown without further investigation
- Date columns contained mixed formats suggesting data from multiple 
  source systems
- Analysis period limited to January 2025 — seasonal trends cannot 
  be assessed
