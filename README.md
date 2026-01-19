 📄 RAG using VectorDB (Chroma) with Groq LLM

A **Retrieval-Augmented Generation (RAG)** system built using **Flowise**, **Chroma Vector Database**, **HuggingFace Embeddings**, and **Groq LLM**.  
This project enables **PDF-based conversational question answering** with memory, caching, and ultra-fast inference.

---



## 🚀 Features

- 📚 PDF document ingestion  
- ✂️ Recursive text chunking  
- 🧠 Embeddings using HuggingFace  
- 🗄️ Chroma Vector Database for similarity search  
- ⚡ High-speed inference using Groq LPU  
- 💬 Conversational memory (chat history aware)  
- 🔁 Follow-up question rephrasing  
- 🧾 Context-grounded answers (no hallucinations)  
- 🧠 In-memory LLM response caching  





## 🏗️ Architecture
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




📂 Project Files
.
├── RAG USING VECTORDB Chatflow.json
├── README.md
