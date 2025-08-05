# Candidate Recommendation Engine

A simple, interactive web app that ranks candidates based on how well their resumes match a given job description. Built using **Streamlit**, **SentenceTransformers**, and **OpenAI GPT 4 mini**.

---

## 🔧 Features

- Input a job description
- Upload multiple resumes (PDF or TXT)
- Generate embeddings with `all-MiniLM-L6-v2` model of sentence-transformer
- Rank resumes using cosine similarity
- AI-generated summary of candidate fit using `gpt-4o-mini`
- Displays top K most relevant candidates with names and scores

---

## Approach

1. **Input Parsing**
   - Resumes are uploaded as PDF or TXT.
   - Text is extracted using PyPDF2 or decoded directly.
   - Candidate name is inferred from the first non-empty line of each resume.

2. **Embedding Generation**
   - Both job descriptions and resumes are embedded using the `sentence-transformers` library (`all-MiniLM-L6-v2`).

3. **Similarity Calculation**
   - Cosine similarity is used to compare the job description against each resume embedding.

4. **Summary Generation**
   - If an OpenAI API key is provided, `gpt-4o-mini` is used to generate a brief explanation of why the candidate is a good fit.

---

## Assumptions

- Resumes are in `.pdf` or `.txt` format.
- Candidate name is taken as the **first non-empty line** of the resume text.
- OpenAI summaries are limited to ~2000 characters of resume content to fit the context window.
- App is run via Streamlit using local or cloud deployment.

---

## Getting Started

### Requirements
- streamlit
- sentence-transformers
- openai 0.28
- PyPDF2

### Installation

```bash
pip install -r requirements.txt

streamlit run app_cv.py

Project Structure
├── app_cv.py                # Main Streamlit app
├── requirements.txt         # Python dependencies
└── README.md                # This file

MIT — free to use and adapt with credit.
