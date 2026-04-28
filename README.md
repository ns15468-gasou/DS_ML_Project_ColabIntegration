# Systematic Literature Review on the Semantic Prioritization of Cybersecurity Indicators
## CSCI 7090 - Team 2
## Nic Recasens & Nigel Smith
## Georgia Southern University

Cyber threats are highly pervasive in today's world. As such, our team aims to train a supervised ML model to help identify these threats through analyzing indicators of spam and phishing.

**Overview**  
Over 8 papers for semantic analysis techniques for spam and phishing detection, we saw that the root data behind that analysis was being neglected in terms of mined info. As such, we prepared 2 datasets to enrich the basic domain metadata of spam mitigation: a known good dataset of popular websites, and a known malicious dataset of known phish attacks, each shaped to achieve the goal of predictive analysis of the future of malicious sites.

Our ML pipeline will primarily focus in on impersonation: identifying impersonated domains with semantic cosine similarity, and using an SVM with lexical extracted features to predict future impersonations.

---

## Table of Contents

```
DS_ML_Project_ColabIntegration/
├── Project/
│   ├── notebooks/
│   │   ├── 1.0_data_preparation_pipeline.ipynb   ← data cleaning & normalization
│   │   ├── 1.1_data_embedding_pipeline.ipynb      ← Gemini embeddings & cosine similarity
│   │   ├── 2.0_ml_pipeline_svm.ipynb              ← SVM impersonation classifier
│   │   └── 2.1_ml_pipeline_clustering.ipynb       ← K-Means attack pattern clustering
│   ├── pdfs/
│   │   ├── Recasens, Smith - Semantic Prioritization of Domain Data...pdf
│   │   └── Recasens, Smith - Lit Review Presentation.pdf
│   ├── data/
│   │   ├── raw_input/
│   │   ├── processed_input/
│   │   └── summarized_output/
│   ├── CourseProject.tex
│   ├── project.bib
│   └── LitReviewOrganizer.csv
└── README.md
```

**Key deliverables:**
- **[Technical Paper](Project/pdfs/Recasens%2C%20Smith%20-%20Semantic%20Prioritization%20of%20Domain%20Data%20for%20Proactive%20Identification%20of%20Cybersecurity%20Indicators.pdf)**
- **[Notebook 1.0 — Data Preparation](Project/notebooks/1.0_data_preparation_pipeline.ipynb)**
- **[Notebook 1.1 — Embedding Pipeline](Project/notebooks/1.1_data_embedding_pipeline.ipynb)**
- **[Notebook 2.0 — SVM Classification](Project/notebooks/2.0_ml_pipeline_svm.ipynb)**
- **[Notebook 2.1 — K-Means Clustering](Project/notebooks/2.1_ml_pipeline_clustering.ipynb)**

---

## Compiling the Paper

```bash
cd Project
pdflatex CourseProject.tex
bibtex project
pdflatex CourseProject.tex
pdflatex CourseProject.tex
```
