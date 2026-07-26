# 🤖 RAG AI Chatbot Powered by Custom LLM Model

A Retrieval-Augmented Generation (RAG) chatbot built using a **custom fine-tuned Microsoft Phi-2 language model**, **ChromaDB**, and **Streamlit**. The chatbot supports querying information from uploaded PDF documents and webpages while also functioning as a general-purpose AI assistant.

---

## 🚀 Features

- ✅ Fine-tuned **Microsoft Phi-2 (2.7B)** using **QLoRA**
- ✅ Retrieval-Augmented Generation (RAG)
- ✅ Upload PDF documents as knowledge base
- ✅ Index webpage content using URL
- ✅ ChromaDB vector database
- ✅ Sentence Transformers embeddings
- ✅ Streamlit interactive interface
- ✅ Switch between:
  - General AI Chat
  - Document Question Answering
- ✅ Memory-efficient 4-bit quantization using BitsAndBytes
- ✅ GPU optimized inference

---

# Project Architecture

```

                User
                  │
        ┌─────────▼─────────┐
        │   Streamlit UI    │
        └─────────┬─────────┘
                  │
      ┌───────────┴───────────┐
      │                       │
      ▼                       ▼
General Chat           Document Search
      │                       │
      ▼                       ▼
Fine-tuned Phi-2       ChromaDB Retriever
      │                       │
      └──────────┬────────────┘
                 ▼
         Custom Prompt Builder
                 │
                 ▼
        Fine-tuned Phi-2 LLM
                 │
                 ▼
             AI Response

```

---

# Tech Stack

| Category | Technology |
|----------|------------|
| Language Model | Microsoft Phi-2 |
| Fine-tuning | LoRA + QLoRA |
| Quantization | BitsAndBytes (4-bit NF4) |
| Framework | HuggingFace Transformers |
| Vector Database | ChromaDB |
| Embeddings | all-MiniLM-L6-v2 |
| Frontend | Streamlit |
| Document Loader | PyMuPDF |
| Web Scraping | Selenium + BeautifulSoup |
| Dataset | tatsu-lab/alpaca |
| Deep Learning | PyTorch |

---

# Model Fine-tuning

The base language model is:

```
microsoft/phi-2
```

The model is fine-tuned using:

- LoRA
- QLoRA
- 4-bit Quantization
- Alpaca Instruction Dataset

### Fine-tuning Configuration

| Parameter | Value |
|------------|--------|
| Model | Phi-2 |
| Dataset | Alpaca |
| Quantization | 4-bit NF4 |
| LoRA Rank | 16 |
| LoRA Alpha | 32 |
| Dropout | 0.05 |
| Learning Rate | 1e-3 |
| Optimizer | AdamW |
| Epochs | 0.2 |
| Max Length | 512 |

---

# Retrieval-Augmented Generation (RAG)

The chatbot follows a standard RAG pipeline:

1. Upload PDF or URL
2. Extract document text
3. Split into chunks
4. Generate embeddings
5. Store vectors in ChromaDB
6. Retrieve relevant chunks
7. Inject retrieved context into prompt
8. Generate answer using fine-tuned Phi-2

---

# Folder Structure

```
rag_ai_chatbot_powered_by_custom_llm_model/
│
├── app.py
├── fine_tuned_llm/
├── chroma_db/
├── requirements.txt
├── README.md
└── assets/
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/rag_ai_chatbot_powered_by_custom_llm_model.git

cd rag_ai_chatbot_powered_by_custom_llm_model
```

---

## Create Virtual Environment

```bash
python -m venv venv

source venv/bin/activate
```

Windows

```bash
venv\Scripts\activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Run Application

```bash
streamlit run app.py
```

---

# Usage

## General Chat

Ask any general AI-related question.

Example:

```
Explain Reinforcement Learning.
```

---

## Document Search

1. Upload PDF
2. Upload URL
3. Select **Document Search**
4. Ask questions related to uploaded content

Example:

```
Summarize Section 3.
```


---

# Fine-tuning Pipeline

```python
Phi-2
      │
      ▼
4-bit Quantization
      │
      ▼
QLoRA
      │
      ▼
Alpaca Dataset
      │
      ▼
Trainer API
      │
      ▼
Fine-tuned Model
```

---

# Technologies Used

- Python
- PyTorch
- Transformers
- PEFT
- LoRA
- QLoRA
- HuggingFace
- Streamlit
- ChromaDB
- Sentence Transformers
- Selenium
- BeautifulSoup
- PyMuPDF
- LangChain
- BitsAndBytes

---

# Future Improvements

- Chat history memory
- Hybrid search (BM25 + Vector Search)
- Reranking models
- Multi-document support
- Streaming token generation
- REST API deployment
- Docker support
- Azure/OpenAI integration
- Agentic RAG workflow
- Evaluation using RAGAS

---

---

# Learning Outcomes

This project demonstrates practical implementation of:

- Large Language Models (LLMs)
- Parameter Efficient Fine-Tuning (PEFT)
- QLoRA
- Retrieval-Augmented Generation
- Vector Databases
- Semantic Search
- Prompt Engineering
- GPU-efficient inference
- HuggingFace ecosystem
- End-to-end AI application development

---

# License

This project is licensed under the MIT License.

---

# Author

**Aparna Ashok Kumar**

M.Tech Data Science | AI/ML Engineer | Generative AI Enthusiast
