# Candidate Recommendation Engine

This app recommends the best candidates for a job based on resume similarity and optional AI summaries.

## Features

- Upload multiple resumes (PDF/TXT)
- Enter job description
- Ranks resumes by cosine similarity using Sentence Transformers
- (Bonus) GPT-4 summaries of candidate fit

## Tech Stack

- Streamlit
- Sentence-Transformers (`all-MiniLM-L6-v2`)
- OpenAI API (optional)
- PyPDF2 (for PDF parsing)

## Setup

```bash
pip install -r requirements.txt
streamlit run app.py

