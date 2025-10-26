# 🧠 DocuMind: Local PDF Insight Engine using FAISS and BLOOM-560M

DocuMind is a **fully local AI-powered PDF insight engine** that allows you to query any document intelligently ,  all without using the internet or external APIs.  
It combines **FAISS** for semantic search and **BLOOM-560M** (a local Hugging Face model) for natural language answers.


## 🚀 Project Overview

 **Purpose:** Build a private, local Retrieval-Augmented Generation (RAG) system for document-based Q&A.  
 **Functionality:** Users can upload a PDF, ask questions, and get accurate responses based only on the document’s content.  
 **Privacy First:** All processing is local - no OpenAI API or cloud dependency.

## ⚙️ Features

| Feature | Description |
|----------|-------------|
| 📄 **PDF Handling** | Extracts text from PDFs using PyPDF2 |
| ✂️ **Text Chunking** | Splits long documents into smaller overlapping chunks for better retrieval |
| 🔍 **Semantic Search (FAISS)** | Builds a FAISS index for similarity-based text search |
| 🧩 **Embeddings** | Uses SentenceTransformers (`all-MiniLM-L6-v2`) for creating text embeddings |
| 🤖 **Local LLM QA** | Uses BLOOM-560M (Hugging Face) to generate human-like answers |
| 🔒 **Fully Offline** | No data leaves your system — everything runs locally |

---

## 🧰 Technologies Used

- **Python 3.10+**
- **Hugging Face Transformers**
- **SentenceTransformers**
- **FAISS**
- **PyPDF2**
- **NumPy**

## 🧠 How It Works

1. **Extract Text:** Load and read PDF content using PyPDF2.  
2. **Chunk Text:** Split text into manageable parts.  
3. **Embed Chunks:** Convert each chunk to a numerical vector using SentenceTransformers.  
4. **Build Index:** Store these vectors in a FAISS index for fast retrieval.  
5. **Query Locally:** When a user asks a question, FAISS retrieves the most relevant chunks.  
6. **Answer Generation:** BLOOM-560M generates a concise answer using only those chunks.


 ## Future Improvements

**Upgrade to larger local models for more context-aware responses**

**Add a Streamlit/Gradio web UI for easy interaction**

**Support multiple PDF uploads**

**Optimize retrieval speed for large datasets**
## 🧪 Example Usage

```python
query = "What teaching method did the master use with students?"
top_chunks = search_faiss(query, k=3)
answer = answer_question_local(query, top_chunks)
print(answer)
