# 📚 Local RAG Pipeline using Ollama

This project implements a **Local Retrieval-Augmented Generation (RAG)** system using **Ollama**.  
The entire pipeline runs **locally**, enabling private, offline-friendly question answering over custom data scraped from the internet.

---

## 🚀 Features

- Runs **fully locally** (no cloud APIs required)
- Uses **LLaMA 3.2 (3B)** model for generation
- Uses **MXBAI Embed Large** for high-quality embeddings
- Web data scraping and preprocessing
- Chunking, embedding, and vector database ingestion
- Retrieval-based context augmentation for accurate responses

---

## 🧠 Model & Embeddings

- **LLM**: `llama3.2:3b` (via Ollama)
- **Embedding Model**: `mxbai-embed-large`

Commands used:
```bash
ollama run llama3.2:3b
ollama pull mxbai-embed-large
```

## 🏗️ RAG Pipeline Architecture

### Workflow

1. **Data Scraping**
   - Scrapes relevant content from the internet (web pages/articles)
   - Cleans and preprocesses raw text data

2. **Chunking**
   - Large documents are split into smaller, meaningful chunks
   - Improves semantic retrieval and embedding efficiency

3. **Embedding**
   - Each chunk is converted into a vector using `mxbai-embed-large`
   - Captures semantic meaning of text data

4. **Vector Database Ingestion**
   - Embedded chunks are stored in a vector database
   - Enables fast similarity-based search

5. **Retrieval + Generation**
   - User query is embedded
   - Relevant chunks are retrieved from the vector database
   - Retrieved context is passed to `llama3.2:3b` for final answer generation

---

## ⚙️ Tech Stack

- **Ollama** – Local LLM and embedding runtime  
- **Python** – Core pipeline implementation  
- **Web Scraping Libraries** – Data collection  
- **Text Splitter** – Chunking documents  
- **Vector Database** – Storing embeddings  
- **RAG Architecture** – Context-aware response generation  

---

## 🎯 Use Cases

- Private document Q&A  
- Research assistant  
- Knowledge base chatbot  
- Offline AI assistant  
- Learning and experimenting with RAG systems  

---

## 📌 Key Highlights

- No external API dependency  
- Complete data privacy  
- Fully local execution  
- Easily extendable to other models and datasets  
- Ideal for academic projects and resume showcasing  

---
## 🧠 Semantic Database (ChromaDB)

This project uses **ChromaDB** as a **semantic vector database** to store and retrieve embeddings efficiently.

### Why ChromaDB?

- Stores high-dimensional embeddings generated using `mxbai-embed-large`
- Enables **semantic similarity search** instead of keyword-based search
- Optimized for Retrieval-Augmented Generation (RAG) pipelines
- Lightweight and easy to run locally

### How it is used in the project

1. Text chunks are converted into embeddings using the Ollama embedding model  
2. These embeddings are stored in **ChromaDB** along with metadata  
3. When a user query is received:
   - The query is embedded
   - ChromaDB retrieves the most semantically similar chunks
4. Retrieved chunks are passed as context to the LLM (`llama3.2:3b`) for response generation

### Role in RAG Pipeline

ChromaDB acts as the **knowledge memory** of the system, enabling accurate and context-aware answers by supplying the most relevant information to the language model.
---

## 📄 Future Improvements

- Add a UI using Streamlit or React  
- Support PDF and DOCX document ingestion  
- Improve chunking and retrieval strategy  
- Add citation-based responses  
- Implement hybrid or reranking search  

---

## 📍 Conclusion

This project demonstrates a complete **Local RAG system** built using Ollama, covering the full pipeline from data scraping to intelligent response generation. It serves as a strong foundation for building privacy-focused AI assistants and experimenting with retrieval-augmented architectures.
