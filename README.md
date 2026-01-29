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

# Hybrid Data Integration
Combined NER-extracted entities with sparse structured database fields.

# Creating Structured Summary
<img width="523" height="583" alt="structured_patient_summary" src="https://github.com/user-attachments/assets/d3f8482a-f7d5-4e09-9f19-820235b579c6" />


