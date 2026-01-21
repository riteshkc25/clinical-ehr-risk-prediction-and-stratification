# clinical-ehr-risk-prediction-and-stratification
A hybrid framework using Transformer-based NLP and clinical scoring rules to predict mortality and length of stay from discharge note. 

# Summary
This project exhibit a comprehensive healthcare AI system that transforms unstructured clinical discharge notes into actionable insights for patient risk assessment. Using state-of-the-art Natural Language Processing (NLP) and transformer models, the system processes 6,000 patient records from the MIMIC-IV database, extracting structured clinical information, generating human-readable summaries, and predicting patient outcomes through both rule-based and hybrid machine learning approaches.

# Data Extraction Process
Data was queried from MIMIC-IV using Google BigQuery SQL to extract relevant clinical information. A subset of 6,000 hospital admissions was extracted to balance computational resources with model development while maintaining statistical validity for risk stratification.
