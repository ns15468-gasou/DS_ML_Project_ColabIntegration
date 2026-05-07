# Systematic Literature Review on the Semantic Prioritization of Cybersecurity Indicators
## CSCI 7090 - Team 2
## Nic Recasens & Nigel Smith
## Georgia Southern University

Cyber threats are highly pervasive in today's world. As such, our team aimed to train a supervised ML model to help identify these threats through analyzing indicators of spam and phishing.

**Overview**  
Over 8 core papers for semantic analysis techniques for spam and phishing detection, we saw that the root data behind that analysis was being neglected in terms of mined info. As such, we prepared 2 datasets to enrich the basic domain metadata of spam mitigation: a known good dataset of popular websites, and a known malicious dataset of known phish attacks, each shaped to achieve the goal of predictive analysis of the future of malicious sites.

Our ML pipeline primarily focused in on impersonation: identifying impersonated domains with semantic cosine similarity, and using an SVM with lexical extracted features to predict future impersonations. However, we also coordinate that with a clustering system to create a holistic view of semantic info from domains.

---

## Table of Contents

```
DS_ML_Project_ColabIntegration/
├── Project/
│   ├── notebooks/
│   │   ├── 1A_data_preparation_pipeline.ipynb  ← Data cleaning & normalization
│   │   ├── 1B_data_embedding_pipeline.ipynb    ← Gemini embeddings & cosine similarity
│   │   ├── 2A_ml_pipeline_svm.ipynb            ← SVM impersonation classifier
│   │   ├── 2B_ml_pipeline_clustering.ipynb     ← K-Means + GBT attack pattern clustering
│   │   └── 3_url_triage_demo.ipynb             ← Combined SVM + K-Means + GBT triage tool
│   │   
│   ├── pdfs/
│   │   ├── Recasens, Smith - Semantic Prior...pdf ← Our final paper
│   │   ├── Recasens, Smith - ... Presentation.pdf ← PDF Versions of our Presentations
│   │   └── ...ipynb.pdf                           ← PDF Versions of our Python Notebooks
│   │   
│   ├── data/ ← Files processed into results by our Notebooks
│   │   ├── raw_input/
│   │   ├── processed_input/
│   │   └── summarized_output/
│   │   
│   ├── CourseProject.tex ← LaTeX source code for our final paper
│   ├── project.bib
│   └── LitReviewOrganizer.csv ← Initial literature review organizer
│      
└── README.md ← You are here!
```

**Key deliverables:**
- **[Final Paper](Project/pdfs/Recasens%2C%20Smith%20-%20Semantic%20Prioritization%20of%20Domain%20Data%20for%20Proactive%20Identification%20of%20Cybersecurity%20Indicators.pdf)**
- **[Notebook 1A — Data Preparation](Project/notebooks/1A_data_preparation_pipeline.ipynb)**
- **[Notebook 1B — Embedding Pipeline](Project/notebooks/1B_data_embedding_pipeline.ipynb)**
- **[Notebook 2A — SVM Classification](Project/notebooks/2A_ml_pipeline_svm.ipynb)**
- **[Notebook 2B — K-Means + GBT Clustering](Project/notebooks/2B_ml_pipeline_clustering.ipynb)**
- **[Notebook 3 — URL Triage Demo](Project/notebooks/3_url_triage_demo.ipynb)**

---

## Compiling the Paper

```bash
cd Project
pdflatex CourseProject.tex
bibtex project
pdflatex CourseProject.tex
pdflatex CourseProject.tex
```
