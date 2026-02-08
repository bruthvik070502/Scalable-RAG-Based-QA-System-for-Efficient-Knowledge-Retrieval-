# Scalable-RAG-Based-QA-System-for-Efficient-Knowledge-Retrieval

# 🔍 LLM-Powered RAG Pipeline

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline using **LlamaIndex**, **OpenAI GPT-3.5**, and **FAISS**, enabling real-time, grounded Q&A over custom document uploads. Designed for flexibility and extensibility, the pipeline currently runs in Google Colab with planned integration to a UI (Gradio or Streamlit).

---

## 🧠 Features

- 📄 **Multi-format document ingestion** (.pdf, .txt, .docx)
- 🔍 **Chunked parsing** and text vectorization using OpenAI embeddings
- ⚡ **FAISS vector store** for high-speed similarity search
- 🧠 **GPT-3.5 Turbo** generates answers grounded in retrieved document context
- 📚 Displays responses alongside supporting source text for traceability

---

## 🧱 Architecture Overview

| Layer              | Component               | Description                                                                 |
|--------------------|-------------------------|-----------------------------------------------------------------------------|
| Document Parsing   | `SimpleDirectoryReader` | Extracts and chunks documents into manageable text segments                 |
| Embedding          | `OpenAIEmbedding`       | Converts chunks into high-dimensional vector embeddings                     |
| Vector Store       | `FAISS`                 | Stores embeddings and performs top-k nearest neighbor retrieval             |
| Index Construction | `VectorStoreIndex`      | Connects FAISS to LLM orchestration using `LlamaIndex`                      |
| Query Execution    | `gpt-3.5-turbo`          | Uses retrieved chunks to construct a prompt and generate a grounded answer  |

---

## 🚀 How It Works

1. Upload documents in `.pdf`, `.txt`, or `.docx` formats.
2. Parse and chunk documents using `SimpleDirectoryReader`.
3. Embed the chunks using `OpenAIEmbedding`.
4. Store the vectors in a FAISS index.
5. For each user query:
   - Retrieve top-k relevant chunks using similarity search.
   - Send the chunks + question to `gpt-3.5-turbo`.
   - Display the generated answer and supporting context.

---

## 📁 File Structure

📦RAG-Pipeline/
┣ 📜rag_pipeline.ipynb # Google Colab notebook
┣ 📁docs/ # Folder for uploaded documents
┣ 📜README.md # Project documentation


---

## 🛠️ Future Plans

- [ ] Add Gradio/Streamlit-based UI for non-technical users  
- [ ] Enable multi-document ingestion and persistent vector store  
- [ ] Support local LLMs (e.g., LLaMA, Mistral) for offline RAG  

---

## 🧪 Requirements

- Python ≥ 3.8  
- OpenAI API key  
- `llama-index`, `faiss-cpu`, `openai`, `tqdm`  
- Google Colab (for current implementation)

---

## 📌 Notes

> This project is for educational and prototyping purposes. Be mindful of OpenAI API rate limits and token costs.

---

## 🤝 Acknowledgments

- [LlamaIndex](https://github.com/jerryjliu/llama_index)  
- [FAISS](https://github.com/facebookresearch/faiss)  
- [OpenAI](https://openai.com/api)



