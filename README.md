# clinical-ehr-risk-prediction-and-stratification
A hybrid framework using Transformer-based NLP and clinical scoring rules to predict mortality and length of stay from discharge note. 

# Summary
This project exhibit a comprehensive healthcare AI system that transforms unstructured clinical discharge notes into actionable insights for patient risk assessment. Using state-of-the-art Natural Language Processing (NLP) and transformer models, the system processes 6,000 patient records from the MIMIC-IV database, extracting structured clinical information, generating human-readable summaries, and predicting patient outcomes through both rule-based and hybrid machine learning approaches.

# Data Extraction
Data was queried from MIMIC-IV using Google BigQuery SQL to extract relevant clinical information. A subset of 6,000 hospital admissions was extracted to balance computational resources with model development while maintaining statistical validity for risk stratification.

# Data Preprocessing
Built CleanicalTextCleaner class usnig regex pattern-remove PHI placeholders, normalized whitespace, fixed punctuation etc. 

# Named Entity Recognition (NER)
Deployed BioClinicalBERT, a transformer based model to extract diagnoses, medications, procedures from free-text discharge notes. Improved data completeness by 12.7%, especially on procedures.

# Hybrid Data Integration & Creating Structured Summary
Combined NER-extracted entities with sparse structured database fields. This extracts entities from discharge text using NER when available
<img width="523" height="583" alt="structured_patient_summary" src="https://github.com/user-attachments/assets/d3f8482a-f7d5-4e09-9f19-820235b579c6" />

# Natural Language Summarization
Deployed BART to generate human-readable clinical summaries. 
<img width="970" height="153" alt="nlp_summary" src="https://github.com/user-attachments/assets/cd766320-cbf3-4398-9011-b2fd2f47f6f6" />

# Clinical Timeline Extraction
Created temporal sequence of events at day level granularity during hospitalization from unstructured data. 
Timeline events: Admission → Diagnosis → Procedures → Medications → Discharge
<img width="882" height="247" alt="clinical_timeline" src="https://github.com/user-attachments/assets/8c6c1084-1e46-4b7b-87c3-95aa1b33928c" />

# Clinical Key Findings Identification
This will automatically flag high-risk patients and critical clinical information. Calculated risk factors include age, comorbidities, polypharmacy, severity scores. Assessed severity levels using SOFA score thresholds.
<img width="563" height="183" alt="clinical_key_findings" src="https://github.com/user-attachments/assets/fa3f3484-18d2-4144-84ed-f4185b4b6cb4" />






