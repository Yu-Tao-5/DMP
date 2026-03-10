💾 DMP-MT: Processed Research Data Management Plans

This repository contains the data processing pipeline and documentation for the DMP-MT project, which focuses on analyzing Research Data Management Plans (DMPs) from research projects.

The goal of this project is to support AI-assisted review and analysis of DMP documents, including tasks such as:

document classification

feedback prediction

document understanding in the Research Data Management (RDM) domain

Due to privacy and confidentiality constraints, the processed dataset itself cannot be publicly shared.
This repository therefore provides the data processing workflow and dataset schema used in the project.

📂 Repository Structure
.
├── Org_Data/           # Original raw DMP documents and source materials
├── processed_data/     # Cleaned and structured dataset (not publicly shared)
├── data_processing.ipynb  # Notebook for dataset preprocessing and transformation
└── README.md
Folder Description

Org_Data/
Contains the original collected data sources related to DMP documents before preprocessing.

processed_data/
Contains the cleaned and structured dataset used for machine learning experiments.
These files are not included in the public repository due to privacy restrictions.

data_processing.ipynb
Notebook that documents the data cleaning, transformation, and structuring process used to convert raw DMP documents into a machine-learning-ready dataset.

🧩 Dataset Schema

Each DMP entry is structured as a JSON object with the following fields:

Field Name	Description
LinkTitle	Unique identifier of the DMP (e.g., D-2021-1000)
ProjectTitle	Title of the research project
Funder	Name of the funding organization (e.g., FWO)
clean_full_text	Cleaned full text extracted from the original DMP document
Status	Submission status of the DMP (e.g., Initial)
InitialDMPReviewStatus	Internal review status (e.g., Reviewed, Pending)
InitialFeedbackHistory	Historical feedback notes (may be empty)
label	Assigned classification label (e.g., good, needs_changes)

All fields are consistently included in each record to ensure a training-ready structure for NLP models.

📊 Example Entry
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

🤖 Intended Use

This dataset structure supports research tasks such as:

DMP quality classification

Automated review assistance for Research Data Management Plans

Document understanding in the RDM domain

Studies on FAIR data practices and research data governance

🔐 Data Availability

The processed dataset contains sensitive institutional documents and therefore cannot be publicly released.

This repository only provides:

the data processing pipeline

the dataset schema

documentation of the data preparation workflow

Researchers interested in Research Data Management Plan analysis may use the provided structure to build their own datasets.
