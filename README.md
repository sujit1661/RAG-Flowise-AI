# 📄 RAG using VectorDB (Chroma) with Groq LLM

A **Retrieval-Augmented Generation (RAG)** system built using **Flowise**, **Chroma Vector Database**, **HuggingFace Embeddings**, and **Groq LLM**.  
This project enables **PDF-based conversational question answering** with memory, caching, and ultra-fast inference.

---

## 🚀 Features

- 📚 **PDF document ingestion** – Upload and process PDF files easily  
- ✂️ **Recursive text chunking** – Break large documents into manageable chunks  
- 🧠 **Embeddings using HuggingFace** – High-quality text vectorization  
- 🗄️ **Chroma Vector Database** – Efficient similarity search for retrieval  
- ⚡ **High-speed inference using Groq LPU** – Ultra-fast LLM responses  
- 💬 **Conversational memory** – Maintains chat history context  
- 🔁 **Follow-up question rephrasing** – Context-aware query reformulation  
- 🧾 **Context-grounded answers** – Reduces hallucinations using retrieved context  
- 🧠 **In-memory caching** – Faster responses for repeated or similar queries  

---

## 🏗️ Architecture

High-level RAG pipeline:

    PDF File
        ↓
    Text Splitter (RecursiveCharacterTextSplitter)
        ↓
    HuggingFace Embeddings
        ↓
    Chroma Vector Store
        ↓
    Retriever
        ↓
    Conversational Retrieval QA Chain
        ↓
    Groq LLM (Chat Model)

---

## 📂 Project Files

    .
    ├── RAG USING VECTORDB Chatflow.json
    └── README.md

---

## ⚙️ Setup Instructions

### 1️⃣ Install Flowise

Install Flowise globally using npm:

    npm install -g flowise

### 2️⃣ Start Flowise

Start the Flowise server:

    flowise start

Then open Flowise in your browser:

    http://localhost:3000

---

### 3️⃣ Import Chatflow

1. Open the **Flowise UI** in your browser.  
2. Click on **Import** in the top-right (or appropriate) menu.  
3. Select and upload: **RAG USING VECTORDB Chatflow.json**.  

This will create the full RAG pipeline for you.

---

### 4️⃣ Configure Credentials

In the Flowise UI, go to **Credentials** and add:

#### 🔹 Groq API

- **Provider**: Groq  
- **API Key**: `GROQ_API_KEY`  

#### 🔹 HuggingFace API

- **Provider**: HuggingFace  
- **API Key**: `HF_API_KEY`  

Make sure both keys are active and have sufficient quota.

---

## 💡 Usage

1. **Upload PDFs**  
   - In the configured chatflow, use the file upload node/step to add one or more PDF documents.  

2. **Ask Questions**  
   - Use the chat interface in Flowise to ask natural language questions about your PDFs.  

3. **Retrieval + Generation**  
   - The system:
     - Splits PDFs into chunks  
     - Creates embeddings with HuggingFace  
     - Stores and retrieves chunks via Chroma  
     - Uses Groq LLM to generate answers grounded in retrieved context  

4. **Conversational Follow-ups**  
   - Ask follow-up questions; the system:
     - Uses conversational memory  
     - Optionally rephrases follow-up questions  
     - Retrieves new relevant context and responds accordingly  

---

## 📌 Notes

- Ensure both **Groq** and **HuggingFace** API keys are valid and correctly set in Flowise.  
- For **large PDFs**, embedding and indexing may take time on first run.  
- In-memory caching improves performance for:
  - Repeated questions  
  - Similar queries over the same document set  
- The system is designed to **minimize hallucinations** by always grounding responses in retrieved context from Chroma.  

---

## 🌐 References

- **Flowise** – Low-code / no-code LLM workflow builder  
- **Chroma Vector Database** – Open-source embedding database for similarity search  
- **HuggingFace Embeddings** – Pretrained models for text embeddings  
- **Groq LLM** – High-speed LPU-accelerated large language model inference
