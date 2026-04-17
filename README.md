# Sofia AI 🤖 — Advanced RAG with LangGraph

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/FastAPI-0.100%2B-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/LangGraph-Latest-orange?style=for-the-badge" alt="LangGraph">
  <img src="https://img.shields.io/badge/Google_Gemini-Powered-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Gemini">
  <img src="https://img.shields.io/badge/PostgreSQL-pgvector-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
</p>

---

**Sofia AI** is a state-of-the-art Retrieval-Augmented Generation (RAG) system engineered for high-performance decision support. Leveraging the cognitive power of **Google Gemini** and the sophisticated cyclic orchestration of **LangGraph**, Sofia processes complex documents to deliver precise, context-aware answers in real-time.

## ✨ Key Features

- 🔄 **Cyclic Graph Orchestration**: Utilizing LangGraph for multi-step reasoning, self-correction, and iterative search refinement.
- ⚡ **High-Performance Vector Search**: Seamless integration with `pgvector` on PostgreSQL for ultra-fast semantic retrieval.
- 📂 **Intelligent Document Ingestion**: Scalable pipeline for processing PDF, DOCX, and Excel files with automated chunking and namespace isolation.
- 🚀 **Modern REST API**: Built on FastAPI with high concurrency support and auto-generated OpenAPI documentation.
- 🕵️ **Native Observability**: Ready for LangSmith integration to provide deep trace inspection and agent debugging.

## 🏗️ System Architecture

The project follows a modular, layer-based architecture designed for scalability and maintainability:

1.  **Agent Layer (`agent/`)**: Orchestrates the control flow, state management, and agentic decision logic.
2.  **Core Layer (`core/`)**: Houses LLM clients (Gemini/OpenAI), prompt templates, and global configurations.
3.  **Ingestion Layer (`ingestion/`)**: Manages the data pipeline—processing, chunking, and indexing documents into the vector store.
4.  **API Layer (`api/`)**: Provides a robust REST interface for real-time interaction and data management.
5.  **Storage Layer (`db/` & `storage/`)**: Handles persistence for both structured data and high-dimensional vector embeddings.

## 🚀 Getting Started

### 1. Prerequisites
- **Docker & Docker Compose**
- **Python 3.10+**
- **Google Gemini API Key** (or OpenAI)

### 2. Spin Up Infrastructure
Launch the PostgreSQL database with `pgvector` support:
```bash
docker-compose up -d
```

### 3. Environment Setup
Initialize your virtual environment and install dependencies:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### 4. Configuration
Clone the environment template and configure your credentials:
```bash
cp .env.example .env
```
> [!IMPORTANT]
> Ensure you set your `GEMINI_API_KEY` in the `.env` file for core functionality.

### 5. Running the Application
**Start the FastAPI Server:**
```bash
uvicorn main:app --reload --port 8000
```
Interactive documentation will be available at: `http://localhost:8000/docs`

**Manual Ingestion Example:**
```bash
python ingestion/pipeline.py --file "data/manual.pdf" --namespace "default"
```

## 🛠️ Tech Stack

- **Orchestration**: LangGraph, LangChain
- **LLM**: Google Gemini (Default), OpenAI (Optional)
- **Database**: PostgreSQL + pgvector
- **API**: FastAPI, Pydantic
- **Processing**: PyMuPDF, Pandas, Tiktoken

## 📜 License
This project is licensed under the [MIT License](LICENSE).

---
<p align="center">Crafted with ❤️ by <a href="https://github.com/GustavoJunio17">Gustavo Junio</a></p>
