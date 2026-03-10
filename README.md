# 💾 DMP-MT: Processed Research Data Management Plans

This repository contains the **data processing pipeline and documentation** for the **DMP-MT project**, which focuses on analyzing **Research Data Management Plans (DMPs)** from research projects.

The goal of this project is to support **AI-assisted review and analysis of DMP documents**, including tasks such as:

- document classification
- feedback prediction
- document understanding in the **Research Data Management (RDM)** domain

---

## 📂 Repository Structure

```bash
.
├── Org_Data/              # Original raw DMP documents and source materials
├── processed_data/        # Cleaned and structured DMP documents
├── data_processing.ipynb  # Notebook for dataset preprocessing and transformation the DMP documents to the JSON ready dataset
└── README.md
```
---

## Folder Description

**Org_Data/**  
Contains the **original collected data sources** related to DMP documents before preprocessing.

**processed_data/**  
Contains the **cleaned DMP documents and structured JSON files** used for machine learning experiments.  
The transformed dataset files are **not included in the public repository due to privacy restrictions**.

**data_processing.ipynb**  
Documents the **data cleaning, transformation, and structuring process** used to convert raw DMP documents into a machine-learning-ready dataset.

---

## 🧩 Dataset Schema

Each DMP entry is structured as a JSON object with the following fields:

| Field Name | Description |
|------------|-------------|
| `LinkTitle` | Unique identifier of the DMP (e.g., `D-2021-1000`) |
| `ProjectTitle` | Title of the research project |
| `Funder` | Name of the funding organization (e.g., `FWO`) |
| `clean_full_text` | Cleaned full text extracted from the original DMP document |
| `Status` | Submission status of the DMP (e.g., `Initial`) |
| `InitialDMPReviewStatus` | Internal review status (e.g., `Reviewed`, `Pending`) |
| `InitialFeedbackHistory` | Historical feedback notes (may be empty) |
| `label` | Assigned classification label (e.g., `good`, `needs_changes`) |

All fields are consistently included in each record to ensure a **training-ready structure for NLP models**.

---

## 📊 Example Entry

```json
{
  "LinkTitle": "D-2021-1000",
  "ProjectTitle": "Rational design of biologics for therapeutic development (FoldCo)",
  "Funder": "FWO",
  "clean_full_text": "This project will explore the use of biologics in therapeutic settings...",
  "Status": "Initial",
  "InitialDMPReviewStatus": "Reviewed",
  "InitialFeedbackHistory": "",
  "label": "good"
}```

- ---

## 🔐 Data Availability

Due to **privacy and confidentiality constraints**, the processed dataset itself **cannot be publicly shared**. This repository therefore provides the **data processing workflow, project structure, and dataset schema** used in the project.

