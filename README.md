# DMP

💾 DMP-MT: Annotated Research Data Management Plans (RDMs)
This dataset consists of anonymized and labeled research data management plans (DMPs) from the DMP-MT project. Each entry includes project metadata, funding information, review feedback, and the full cleaned text of the original document.

The dataset is structured for supervised machine learning tasks such as classification, feedback prediction, and document understanding in the research data management domain.

🧩 Dataset Structure
Each sample in the dataset is a JSON object with the following fields:

Field Name	Description
LinkTitle	Unique identifier of the DMP (e.g., "D-2021-1000")
ProjectTitle	Title of the research project
Funder	Name of the funding organization (e.g., "FWO")
clean_full_text	Cleaned and extracted full text content of the DMP
Status	Submission status of the DMP (e.g., "Initial")
InitialDMPReviewStatus	Internal review status (e.g., "Reviewed", "Pending")
InitialFeedbackHistory	Text field capturing historical feedback notes (may be empty but included)
label	Assigned classification label (e.g., "good", "needs_changes", etc.)
All fields are consistently included per record to ensure training-ready structure for NLP models.

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
This dataset can be used for:

Fine-tuning classification models (e.g., quality labeling of DMPs)

Document understanding and extraction tasks

Research on open science, FAIR data practices, or metadata enrichment

🔐 Data Notes
All documents have been anonymized to remove personally identifiable information. Feedback history may be empty but is preserved to maintain a consistent schema.

📚 Citation
@dataset{dmp_mt_2025, title = {DMP-MT: Annotated Research Data Management Plans}, author = {Yu Tao et al.}, year = {2025}, publisher = {Hugging Face}, url = {https://huggingface.co/datasets//} }
