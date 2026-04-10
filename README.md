# Systematic Literature Review on the Semantic Prioritization of Cybersecurity Indicators  
## CSCI 7090 - Team 2  
## Nic Recasens & Nigel Smith  
## Georgia Southern University  

Cyber threats are highly pervasive in today's world. As such, our team aims to train a supervised ML model to help identify these threats through analyzing indicators of spam and phishing.

**Overview**  
Over 8 papers for semantic analysis techniques for spam and phishing detection, we saw that the root data behind that analysis was being neglected in terms of mined info. As such, we prepared 2 datasets to enrich the basic domain metadata of spam mitigation: a known good dataset of popular websites, and a known malicious dataset of known phish attacks, each shaped to achieve the goal of predictive analysis of the future of malicious sites.

Our ML pipeline will primarily focus in on impersonation: identifying impersonated domains with semantic cosine similarity, and using an SVM with lexical extracted features to predict future impersonations. 

**Compiling - cd to folder containing LiteratureReview.tex and litreview.bib**

```
pdflatex LiteratureReview.tex  
bibtex litreview  
pdflatex LiteratureReview.tex  
pdflatex LiteratureReview.tex
```