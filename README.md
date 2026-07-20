# A Multi-Agent Retrieval-Augmented Framework for Intelligent Resume Screening and Candidate Evaluation

## Overview

This repository contains the implementation of our research work on **AI-powered resume screening and candidate evaluation** using Large Language Models (LLMs).

The proposed framework aims to improve automated recruitment by integrating:

- Multi-Agent Retrieval-Augmented Generation (RAG)
- Dynamic Domain-Based Weighted Resume Scoring
- Dynamic Annotator Ground Truth Generation

The implementation has been evaluated on the **CareerCorpus** dataset using multiple regression and ranking metrics.

---

# Proposed Methodologies

## Proposed Method I – Multi-Agent RAG LLM

This methodology implements a Retrieval-Augmented Generation (RAG) based Multi-Agent framework for intelligent resume evaluation.

### Workflow

- Resume Preprocessing
- FAISS Knowledge Base Creation
- Resume Evaluation Agent
- CEO Agent
- CTO Agent
- HR Agent
- Hiring Coordinator
- Candidate Recommendation

### Technologies

- Python
- OpenRouter API
- DeepSeek-V3
- FAISS
- BAAI BGE Embeddings
- Pandas
- NumPy

### Evaluation Metrics

- Pearson Correlation
- Spearman Correlation
- MAE
- RMSE
- R² Score
- PC20 / SC20
- PC15 / SC15
- PC10 / SC10

---

## Proposed Method II – Dynamic Weighted Resume Scoring

The second methodology introduces a dynamic weighting strategy for resume evaluation.

Instead of assigning equal importance to every resume attribute, the framework dynamically generates feature weights according to:

- Job Domain
- Job Level

The final resume score is calculated using

\[
G(R_j)=\sum_{k=1}^{K}w_kf_k(R_j)
\]

where

- \(f_k(R_j)\) = score of feature \(k\)
- \(w_k\) = dynamically generated weight

### Resume Features

- Education
- Skills
- Experience
- Projects
- Certifications
- Domain Knowledge

Generated weights are cached and reused for resumes belonging to the same job category to reduce API calls.

---

## Proposed Method III – Dynamic Annotator Ground Truth

Traditional approaches compute the ground truth using the arithmetic mean of multiple annotator scores.

This work proposes a Dynamic Ground Truth generation approach using:

- Sentence-BERT Embeddings
- Semantic Resume Retrieval
- Median Absolute Deviation (MAD)
- Dynamic Annotator Weighting

Instead of treating every annotator equally, annotator consistency is estimated and converted into adaptive weights before calculating the final ground truth score.

---

# Dataset

The experiments were conducted using the **CareerCorpus** dataset.

Dataset Contents include:

- Education
- Skills
- Experience
- Job Domain
- Job Level
- Human Annotator Scores

---

# Repository Structure

```
Multi-Agent-Resume-Hiring

├── Proposed Method I - Multi-Agent RAG LLM
│   ├── Source Code
│   ├── Input Files
│   ├── Output Files
│   ├── Graphs
│   └── Result Metrics
│
├── Proposed Method II - Dynamic Weighted Scoring
│   ├── Source Code
│   ├── Input Files
│   ├── Output Files
│   ├── Graphs
│   └── Result Metrics
│
├── Proposed Method III - Dynamic Annotator Ground Truth
│   ├── Source Code
│   ├── Input Files
│   ├── Output Files
│   ├── Graphs
│   └── Result Metrics
│
└── README.md
```

---

# Installation

Install the required Python packages

```bash
pip install -r requirements.txt
```

or install manually

```bash
pip install pandas
pip install numpy
pip install scikit-learn
pip install sentence-transformers
pip install faiss-cpu
pip install openai
pip install matplotlib
pip install scipy
```

---

# Running the Project

## Proposed Method I

Run

```
Method1_MultiAgent_RAG_LLM.ipynb
```

Outputs

- Resume Evaluation Scores
- Candidate Recommendations
- JSON Report
- Evaluation Metrics

---

## Proposed Method II

Run

```
Method2_Dynamic_Weighted_Scoring.ipynb
```

Outputs

- Dynamic Feature Weights
- Dynamic Resume Scores
- JSON Results
- CSV Results

---

## Proposed Method III

Run

```
Method3_Dynamic_Annotator_GroundTruth.ipynb
```

Outputs

- Dynamic Ground Truth
- Updated Evaluation Metrics
- JSON Results
- CSV Results

---

# Evaluation Metrics

The proposed methodologies are evaluated using:

- Pearson Correlation
- Spearman Correlation
- Mean Absolute Error (MAE)
- Root Mean Square Error (RMSE)
- Coefficient of Determination (R²)
- PC20
- SC20
- PC15
- SC15
- PC10
- SC10

---

# Research Contributions

- Multi-Agent Retrieval-Augmented Resume Evaluation
- Dynamic Domain-Specific Feature Weight Generation
- Dynamic Annotator Ground Truth Generation
- Improved Resume Ranking using Adaptive Scoring
- Explainable and Transparent Candidate Evaluation

---

# Authors

**Mateti Karthik**

B.Tech in Computing and Data Science

Sai University, Chennai, India

---

# Citation

If you use this repository in your research, please cite the corresponding paper once published.

---

# License

This project is intended for academic and research purposes.
