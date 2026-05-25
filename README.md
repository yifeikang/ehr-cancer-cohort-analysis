# Synthetic EHR Cancer Cohort Analysis
[![Build Status](https://github.com/yifeikang/ehr-cancer-cohort-analysis/actions/workflows/main.yml/badge.svg)](https://github.com/yifeikang/ehr-cancer-cohort-analysis/actions/workflows/main.yml)


Exploratory analysis of synthetic longitudinal electronic health record (EHR) data to identify and characterize patients with cancer using Python-based healthcare analytics workflows.

---

## Project Overview

This project analyzes the Synthea synthetic EHR dataset to:

- Explore longitudinal healthcare data structure
- Define a rule-based cancer cohort
- Characterize patient demographics and healthcare utilization
- Demonstrate reproducible cohort engineering workflows
- Discuss limitations and real-world EMR cohort refinement strategies

---

## Objectives

1. Explore the structure and contents of the Synthea EHR dataset
2. Identify patients with cancer using diagnosis-based and code-based cohort definitions
3. Analyze:
   - demographics
   - cancer types
   - age at diagnosis
   - healthcare utilization
   - longitudinal follow-up
4. Discuss methods for improving cohort specificity in real-world EMR systems

---

## Technologies Used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook

---

## Repository Structure

```text
ehr-cancer-cohort-analysis/
│
├── data/
│   ├── raw/
│   │   └── (source CSV files)
│   └── processed/
│       └── (derived tables and analysis outputs)
│
├── notebooks/
│   └── cancer_cohort_notebook.ipynb
│
├── figures/
│   ├── age_at_diagnosis.png
│   ├── cancer_type_distribution_by_gender.png
│   ├── encounter_distribution.png
│   └── validated_age_comparison.png
│
├── presentation/
│   └── synthea_presentation.pptx
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Dataset

Synthetic EHR data generated using Synthea.

Source:
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/BWDKXS

Dataset used:
- `synthea-patient-pop1-csv.zip`

---

## Data Setup

1. Download the dataset from Harvard Dataverse
2. Extract the CSV files
3. Place the raw CSV files into `data/raw/`
4. Save derived tables, cleaned extracts, or intermediate outputs in `data/processed/`

Example:

```text
data/raw/
├── patients.csv
├── conditions.csv
├── encounters.csv
├── medications.csv
├── procedures.csv
└── observations.csv

data/processed/
└── cohort_flow_summary.csv
```

---

## Cohort Definition

Cancer patients were identified using diagnosis terminology from the `CONDITIONS` table.

Keyword-based filtering included terms such as:

- cancer
- malignant
- carcinoma
- neoplasm
- leukemia
- lymphoma
- melanoma

The first qualifying diagnosis date was used as the index cancer diagnosis date.

---

## Analytical Workflow

1. Load and inspect EHR tables
2. Clean and standardize date variables
3. Identify cancer-related diagnoses
4. Create patient-level cancer cohort
5. Calculate age at diagnosis and follow-up
6. Generate descriptive statistics and visualizations
7. Evaluate healthcare utilization patterns
8. Discuss limitations and cohort refinement strategies

---

## Key Analyses

### Demographics
- Age distribution
- Sex distribution
- Race and ethnicity distribution

### Cancer Cohort Characterization
- Cancer subtype frequency
- Age at diagnosis
- Longitudinal follow-up duration

### Healthcare Utilization
- Encounter frequency
- Procedures
- Medications
- Comorbidity burden

---

## Limitations

This analysis uses synthetic EHR data and a diagnosis-based cohort definition.

Potential limitations include:

- Rule-out diagnoses
- Incomplete disease confirmation
- Lack of pathology reports
- Simplified coding structure
- Absence of unstructured clinical notes

---

## Real-World EMR Refinement Strategies

In a production healthcare environment, cohort validation could be improved using:

- Pathology reports
- Oncology medications
- Chemotherapy administration records
- Tumor registry data
- ICD/SNOMED mappings
- Temporal validation logic
- NLP on clinical notes
- Manual chart review

---

## Reproducibility

This project was designed with reproducibility and transparency in mind:

- Notebook-based workflow
- Modular analysis structure
- Documented cohort logic
- Version-controlled code
- Reusable Python functions

---

## Running the Analysis

Install required packages:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
notebooks/cancer_cohort_notebook.ipynb
```

---

## Author

Yifei Kang
