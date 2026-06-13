# AI PDF Chatbot

RAG-based conversational question-answering system for multiple PDF documents.

The app lets a user upload PDFs, extracts text, chunks the content, builds a FAISS vector index, and answers natural-language questions using a conversational retrieval flow.

## What It Demonstrates

- Retrieval-Augmented Generation over user-uploaded documents
- Multi-PDF ingestion and text extraction
- Chunking strategy for long documents
- FAISS-based semantic retrieval
- Conversation memory for follow-up questions
- Streamlit product interface for a document QA workflow

## Architecture

```text
PDF uploads
  -> text extraction
  -> chunking
  -> embeddings
  -> FAISS vector store
  -> conversational retrieval chain
  -> Streamlit chat UI
```

## Tech Stack

Python, Streamlit, PyPDF2, LangChain, FAISS, OpenAI embeddings, Hugging Face instruction embeddings, conversational memory.

## Run Locally

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Create a local environment file:

```bash
cp .env.example .env
```

3. Add the required API key or embedding configuration.

4. Start the app:

```bash
streamlit run app.py
```

## Recruiter Notes

This is a clean applied RAG project: it shows document ingestion, retrieval, vector search, and an end-user workflow. It is relevant for AI assistant, enterprise search, legal/finance document QA, and knowledge-base chatbot roles.

## Next Improvements

- Add evaluation questions for retrieval quality
- Add source citation display
- Add Docker setup for reproducible deployment
- Add sample screenshots or a short demo GIF
