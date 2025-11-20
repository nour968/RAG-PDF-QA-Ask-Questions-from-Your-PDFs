# RAG-PDF-QA-Ask-Questions-from-Your-PDFs
This project lets you ask natural language questions about the contents of a PDF and get answers instantly using Retrieval-Augmented Generation (RAG)!

# 🚀 Overview

This project lets you ask natural language questions about the contents of a PDF and get answers instantly using Retrieval-Augmented Generation (RAG)!
It combines:

Mistral Nemo: Powerful causal language model for text generation.

Sentence Transformers: For embedding PDF chunks into vectors.

FAISS: Lightning-fast vector search for retrieving relevant text.

FastAPI + Ngrok: Instant API hosting to query your PDFs online.

You can upload any PDF, ask a question, and get answers sourced directly from your documents. Perfect for research papers, manuals, or university guides!

# 🎬 Video Preview
[UI](https://github.com/user-attachments/assets/5a27c8c2-ae9f-4b39-b5a8-2a4660603e07)

# ⚡ Features

Extracts text from any PDF file.

Splits text into overlapping chunks for more accurate retrieval.

Embeds chunks into high-dimensional vectors using Sentence Transformers.

Creates a FAISS vector index for ultra-fast similarity search.

Retrieves the most relevant chunks for a given question.

Generates answers with Mistral Nemo model.

Fully deployable as a FastAPI endpoint via Ngrok.

# 🛠️ Installation
pip install torch transformers sentence-transformers PyPDF2 faiss-cpu fastapi uvicorn pyngrok requests

# 📝 Usage
1. Run FastAPI server
uvicorn app:app --reload

2. Ask a question

Send a POST request to /rag with:

file: PDF file

question: Your query

import requests

URL = "<YOUR_NGROK_URL>/rag"
files = {"file": open("Tips Hindawi University Info.pdf", "rb")}
data = {"question": "Where is Tips Hindawi University located?"}

response = requests.post(URL, files=files, data=data)
print(response.json())

# 🧩 How It Works

PDF Extraction – Reads PDF text using PyPDF2.

Chunking – Splits text into smaller overlapping sections.

Embedding – Converts chunks into embeddings with Sentence Transformers.

FAISS Search – Finds top-k similar chunks for the query.

RAG Answering – Generates answers from the selected chunks using Mistral.

# 💡 Example Output
Question: Where is Tips Hindawi University located?
Answer: Tips Hindawi University is located in [city, country]...

# 🔗 Live Demo

Access your FastAPI endpoint anywhere via Ngrok!
Your public URL: https://your-ngrok-url.ngrok-free.app/rag

🏷️ Keywords

#RAG #PDFQA #MistralNemo #FAISS #SentenceTransformers #FastAPI #Ngrok #Python #AI #DocumentSearch
