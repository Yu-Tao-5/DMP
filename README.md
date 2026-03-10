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

## ⚙️ Data Processing Pipeline

The dataset was constructed through a multi-stage preprocessing pipeline...

Raw DMP Documents
        ↓
PDF Standardization
        ↓
PDF → JSON Parsing
        ↓
Feedback Integration
        ↓
Label Assignment
        ↓
Dataset Construction
        ↓
Train / Dev / Test
        ↓
Hugging Face Dataset

### Step 1: Pre-Setting
...

The dataset was constructed through a multi-stage preprocessing pipeline to transform heterogeneous DMP documents and review records into a structured dataset suitable for machine learning.

The overall workflow is summarized below.

### Step 1: Pre-Setting
Initial environment setup, including directory structure, library imports, and configuration of processing parameters.

### Step 2: Standardize All Initial Files into PDFs
Original DMP documents were collected in multiple formats (e.g., Word, PDF).  
All files were standardized into **PDF format** to ensure consistent downstream processing.

### Step 3: Convert All PDFs to JSON (Unstructured)
Each PDF was processed using a document parsing tool to extract text and structural information.  
The outputs were stored as **JSON files**, preserving paragraph-level text content.

### Step 4: Analyze Feedback and Assign Labels to Original Data

#### 4.1 Explore the raw feedback `json.txt` file
Inspection of the original feedback data exported from the internal review system.

#### 4.2 Merge Excel Columns into JSON & Inspect `InitialDMPReviewStatus`
Feedback data from Excel tables was merged with JSON records to associate each DMP with its corresponding review information.

#### 4.3 Filter and Generate Review JSON Files
Filtering of relevant feedback fields and generation of structured review JSON files.

#### 4.4 Resolve Status Discrepancies
Comparison between the **original JSON metadata** and the **Excel review records** to resolve inconsistencies and produce the final review dataset.

### Step 5: Build Dataset Records and Split into Train/Dev/Test
After cleaning and merging all sources, the dataset was structured into machine-learning-ready records and split into:

- Training set
- Development set
- Test set

### Step 6: Ready for Hugging Face Dataset
The final dataset format follows the **Hugging Face dataset schema**, making it directly compatible with NLP model training and evaluation pipelines.


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
}
```
- ---

## 🔐 Data Availability

Due to **privacy and confidentiality constraints**, the processed dataset itself **cannot be publicly shared**. This repository therefore provides the **data processing workflow, project structure, and dataset schema** used in the project.

