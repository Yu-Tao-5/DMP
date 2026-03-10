# 💾 DMP-MT: Processed Research Data Management Plans

This repository contains the **data processing pipeline and documentation** for the **DMP-MT project**, which focuses on analyzing **Research Data Management Plans (DMPs)** from research projects.

The goal of this project is to support **AI-assisted review and analysis of DMP documents**, including tasks such as:

- document classification
- feedback prediction
- document understanding in the **Research Data Management (RDM)** domain

Due to **privacy and confidentiality constraints**, the processed dataset itself **cannot be publicly shared**. This repository therefore provides the **data processing workflow, project structure, and dataset schema** used in the project.

---

## 📂 Repository Structure

```bash
.
├── Org_Data/              # Original raw DMP documents and source materials
├── processed_data/        # Cleaned and structured dataset (not publicly shared)
├── data_processing.ipynb  # Notebook for dataset preprocessing and transformation
└── README.md

---

## Folder Description

**Org_Data/**  
Contains the **original collected data sources** related to DMP documents before preprocessing.

**processed_data/**  
Contains the **cleaned and structured dataset** used for machine learning experiments.  
These files are **not included in the public repository due to privacy restrictions**.

**data_processing.ipynb**  
Documents the **data cleaning, transformation, and structuring process** used to convert raw DMP documents into a machine-learning-ready dataset.
