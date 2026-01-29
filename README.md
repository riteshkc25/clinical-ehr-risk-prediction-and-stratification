# clinical-ehr-risk-prediction-and-stratification
A hybrid framework using Transformer-based NLP and clinical scoring rules to predict mortality and length of stay from discharge note. 

# Summary
This project exhibit a comprehensive healthcare AI system that transforms unstructured clinical discharge notes into actionable insights for patient risk assessment. Using state-of-the-art Natural Language Processing (NLP) and transformer models, the system processes 6,000 patient records from the MIMIC-IV database, extracting structured clinical information, generating human-readable summaries, and predicting patient outcomes through both rule-based and hybrid machine learning approaches.

# Data Extraction
Data was queried from MIMIC-IV using Google BigQuery SQL to extract relevant clinical information. A subset of 6,000 hospital admissions was extracted to balance computational resources with model development while maintaining statistical validity for risk stratification.

# Data Preprocessing
Built CleanicalTextCleaner class usnig regex pattern-remove PHI placeholders, normalized whitespace, fixed punctuation etc. 

# Named Entity Recognition (NER)
Deployed BioClinicalBERT, a transformer based model to extract diagnoses, medications, procedures from free-text discharge notes.

# Hybrid Data Integration
Combine NER-extracted entities with sparse structured database fields. Improved data completeness by 12.7%, especially on procedures.

# Creating Structured Summary
Created simple structured summary as follows:
============================================================
PATIENT SUMMARY - ID: 10000980-DS-26
============================================================
DEMOGRAPHICS:
  • Subject ID: 10000980
  • Age: 80 years
  • Gender: female
  • Length of Stay: 2 days
DIAGNOSES (22 total):
  1. kidney disease
  2. peripheral vascular disease
  3. diabetic retinopathy
  4. heart failure
  5. artery disease
  ... and 17 more
MEDICATIONS (22 total):
  1. bromide
  2. insulin
  3. tor
  4. carvedilol
  5. torsemide
  ... and 17 more
SEVERITY ASSESSMENT:
  • SOFA Score: nan
  • OASIS Score: nan
  • Data Completeness: 50%
OUTCOME:
  • Hospital Death: No


