# Multi-Agent Resume Hiring

This repository contains the implementation of our research project:

**A Multi-Agent Retrieval-Augmented Framework for Intelligent Resume Screening and Candidate Evaluation**

The project proposes three methodologies for intelligent resume screening using Large Language Models (LLMs):

- Multi-Agent RAG LLM Resume Evaluation
- Domain Weighted Resume Scoring
- Dynamic Annotator Ground Truth

The implementation is evaluated using the CareerCorpus dataset.

---

# Repository Structure

```
Multi-Agent-Resume-Hiring

│
├── Multi Agent Rag LLM
│   ├── Graphs and visualization
│   │   ├── 01_graph_multiagent.png
│   │   ├── 02_graph_multiagent.png
│   │   ├── 03_graph_multiagent.png
│   │   ├── 04_graph_multiagent.png
│   │   └── 05_graph_multiagent.png
│   │
│   ├── Input files
│   │   └── CareerCorpus.xlsx
│   │
│   ├── Result Metrics
│   │   └── Screenshot 2026-07-12....
│   │
│   ├── output files
│   │   ├── complete_pipeline_results.json
│   │   └── evaluation_results.csv
│   │
│   └── Updated Multi LLMs resume ...
│
├── Domain Weighted Scoring LLM
│   ├── Graphs and visualization
│   │   ├── 01_graph_dynamicweight.png
│   │   ├── 02_graph_dynamicweight.png
│   │   ├── 03_graph_dynamicweight.png
│   │   └── 04_graph_dynamicweight.png
│   │
│   ├── Input files
│   │   └── complete_pipeline_results.json
│   │
│   ├── Result Metrics
│   │   └── Screenshot 2026-07-12....
│   │
│   ├── output files
│   │   ├── dynamic_pipeline_results.json
│   │   └── dynamic_resume_scores.csv
│   │
│   └── Updated dynamic weights for...
│
├── Annotator dynamic Ground truth
│   ├── Dynamic domain Dynamic Annotator
│   │   ├── Graphs and visualization
│   │   ├── Input files
│   │   ├── Result Metrics
│   │   └── output files
│   │
│   ├── Multi Agent Rag LLM Dynamic Annotator
│   │
│   ├── Single LLM Dynamic Annotator
│   │
│   ├── Annotator GroundtruthGT.ipynb
│   │
│   └── CareerCorpus_DynamicGT.csv
│
└── README.md
```

---

# Proposed Method I – Multi Agent Rag LLM

This methodology implements a Retrieval-Augmented Generation (RAG) based multi-agent framework for intelligent resume evaluation.

### Workflow

- Resume Preprocessing
- FAISS Knowledge Base
- Resume Evaluation Agent
- CEO Agent
- CTO Agent
- HR Agent
- Hiring Coordinator
- Candidate Recommendation

### Input

- CareerCorpus.xlsx

### Output

- complete_pipeline_results.json
- evaluation_results.csv

---

# Proposed Method II – Domain Weighted Scoring LLM

This methodology introduces dynamic domain-specific resume scoring.

Instead of assigning equal importance to every resume feature, the framework dynamically generates weights according to the job domain and job level before computing the final score.

The final resume score is computed as

\[
G(R_j)=\sum_{k=1}^{K}w_kf_k(R_j)
\]

where

- \(f_k(R_j)\) is the score of the kth resume feature.
- \(w_k\) is the dynamically generated feature weight.

### Input

- complete_pipeline_results.json

### Output

- dynamic_pipeline_results.json
- dynamic_resume_scores.csv

---

# Proposed Method III – Annotator dynamic Ground truth

Traditional evaluation computes the ground truth by averaging multiple annotator scores.

This methodology proposes a Dynamic Ground Truth generation strategy using

- Sentence-BERT
- Semantic Resume Retrieval
- Median Absolute Deviation (MAD)
- Dynamic Annotator Weighting

Three evaluation pipelines are included:

- Dynamic domain Dynamic Annotator
- Multi Agent Rag LLM Dynamic Annotator
- Single LLM Dynamic Annotator

### Input

- CareerCorpus_DynamicGT.csv

### Output

Dynamic evaluation results for all three pipelines.

---

# Dataset

CareerCorpus Dataset

The dataset contains

- Education
- Skills
- Experience
- Job Domain
- Job Level
- Human Annotator Scores

---

# Evaluation Metrics

The framework is evaluated using

- Pearson Correlation
- Spearman Correlation
- MAE
- RMSE
- R² Score
- PC20
- SC20
- PC15
- SC15
- PC10
- SC10

---

# Technologies Used

- Python
- OpenRouter API
- DeepSeek-V3
- FAISS
- Sentence Transformers
- BGE Embeddings
- Pandas
- NumPy
- Scikit-learn
- Matplotlib

---

# Authors

1. **Oindrila Chakraborty**  
   Msc.Data Science (2025-2027)  
   St.Xavier’s College (Autonomous) Kolkata

2. **Mateti Karthik**  
   B.Tech in Computing and Data Science (2024–2028)  
   Sai University, Chennai, India
   
4. **Kotha Avaneesh Reddy**  
   B.Tech in Computing and Data Science (2024–2028)  
   Sai University, Chennai, India

5. **T. Jaya Chandrika**  
   5 years integrated Data science   
   Teri school of advanced studies (New Delhi)

6. **Sujitha P**  
   B.tech Artificial Intelligence and Data Science(2024-2028)
   Sri Eshwar college of Engineering, Coimbatore

7. **G Charit**  
   Btech Computer science 2024-2028
   Gitam University vizag

8. **Ala Mahesh**  
   Btech in computer science and engineering (2025-2029)
   Indian institute of information technology Kottayam, Kottayam

# License

This repository is intended for academic and research purposes.
