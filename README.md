# END-TO-END-DATA-SCIENCE-PROJECT

Company: CODTECH IT SOLUTIONS 
Name: Jonna Nikhil 
Intern Id: CT04DF1123 
Domain: Data Science 
Duration: 4 Weeks 
Mentor: Neela Santhosh

#Task 3 – END-TO-END-DATA-SCIENCE-PROJECT
# SMART RESUME ANALYZER

**Company**: CODTECH IT SOLUTIONS  
**Name**: Jonna Nikhil  
**Intern ID**: CT04DF1123  
**Domain**: Data Science  
**Duration**: 4 Weeks  
**Mentor**: Neela Santhosh  

---

## Task 3 – END-TO-END DATA SCIENCE PROJECT  
**Project Title**: Smart Resume Analyzer Using NLP and Flask

---

## Goal

The objective of this project is to build an **end-to-end machine learning application** capable of analyzing and ranking resumes based on how well they match a given job description. It leverages **Natural Language Processing (NLP)** for semantic analysis and **Flask** for deployment in a real-time web environment.

The system supports:
- Uploading multiple resumes in **PDF format**
- Entering a custom **job description**
- Analyzing the **semantic similarity** between each resume and the job description
- Ranking resumes from highest to lowest match
- Displaying the output in a user-friendly web interface

---

## Input Dataset

This is a custom-input project with two main data inputs:
1. **Job Description** (text typed into the web interface)
2. **Resume Documents** in `.pdf` format uploaded by the user (can be multiple)

No static dataset is required; all data is dynamic and user-provided.

---

## About the Project

This project simulates a practical HR screening system. It automates the first level of resume filtering based on how closely a candidate’s resume aligns with the job description.

Key Components:
- **Resume Parsing**: Uses `PyMuPDF` to extract clean text from PDFs.
- **Semantic Encoding**: Uses `sentence-transformers` (BERT-based models) to convert both resumes and the job description into embeddings.
- **Similarity Calculation**: Uses **cosine similarity** to compare each resume with the job description and rank them accordingly.
- **Deployment**: Built and served using **Flask**, providing a simple and effective user interface to interact with the model.

---

## What I Had Done

### Data Collection
- Multiple resumes are uploaded in `.pdf` format by the user.
- Job description is typed into the input box by the recruiter.

### Preprocessing
- All resumes are parsed and cleaned.
- Text is converted into dense numerical vectors using **BERT-based sentence transformers**.
- Missing values, encoding errors, and parsing inconsistencies are handled.

### Model Design & Scoring
- The model computes **cosine similarity** between each resume vector and the job description vector.
- Resumes are ranked from best match to least based on similarity scores.
- Optionally highlights matched keywords (skill-based extraction using spaCy).

### Deployment
- The entire system is deployed using **Flask**.
- A clean interface allows for:
  - Job description entry
  - Drag-and-drop PDF upload
  - Result display with score-based ranking

---

## Libraries Used

```text
streamlit             # (Used earlier for prototyping)
sentence-transformers # To generate semantic embeddings
PyMuPDF               # For PDF parsing
rapidfuzz             # Optional fuzzy matching
fpdf                  # For optional report generation
spacy                 # For entity recognition and skill extraction
python-dateutil       # Date parsing utility
```

> Model: BERT-based `sentence-transformers/paraphrase-MiniLM-L6-v2`

---

## Exploratory Results & User Interface

### UI Screenshot – Web Interface:


### Sample Output – Resume Match Ranking

| Resume File              | Match % |
|--------------------------|---------|
| Abhinav_Kohali_resume.pdf | 88.2%   |
| Abhishek_resume.pdf       | 86.4%   |
| Harsh_Rajput_resume.pdf   | 81.0%   |

---

##  Evaluation Criteria

| Metric             | Description                              |
|--------------------|------------------------------------------|
| Cosine Similarity  | Measures semantic closeness of texts     |
| Keyword Match      | (Optional) Based on fuzzy/regex matching |
| Named Entity Match | (Optional) via spaCy NER                 |

---

##  Output

-  Resumes sorted by similarity to the job description
-  Results displayed in real-time in the web interface
-  Optionally, display extracted skills and named entities

---

##  Project Workflow

```
Job Description + Resume PDFs
          ↓
    Text Extraction (PyMuPDF)
          ↓
  Sentence Embeddings (BERT)
          ↓
 Cosine Similarity Computation
          ↓
     Resume Ranking Output
          ↓
    Web App Display (Flask)
```

---

## Conclusion

This project demonstrates a full end-to-end application cycle of data science in real-world automation:

- ✔️ Handles real-time input from users (text + files)
- ✔️ Uses modern NLP models (BERT) for smart analysis
- ✔️ Deploys using Flask, making it usable in browser
- ✔️ Enhances hiring efficiency and decision-making

The Smart Resume Analyzer is a powerful tool for simplifying early-stage resume screening and highlights the practical application of machine learning and NLP.

---

## Project Structure

```
/resume-analyzer-task3/
├── app.py
├── resume_analyzer.py
├── utils.py
├── requirements.txt
├── templates/
│   ├── index.html
│   └── result.html
├── static/
│   └── style.css
├── sample_resumes/
│   ├── Abhishek_resume.pdf
│   ├── Harsh_Rajput_resume.pdf
│   └── Abhinav_Kohali_resume.pdf
└── screenshots/
    └── app_ui.png
```

---

## How to Run This Project Locally

```bash
# Clone the repository

# Install dependencies
pip install -r requirements.txt
python -m spacy download en_core_web_sm

# Run Flask server
python app.py
```

---
