# 📄 Document Question Answering System

A Retrieval-Augmented Generation (RAG) based Document Question Answering System that answers user questions from PDF documents using semantic search and Google Gemini.

---

## 📌 Overview

This project implements a simple Retrieval-Augmented Generation (RAG) pipeline that allows users to ask questions about a PDF document.

Instead of relying only on a Large Language Model (LLM), the system first retrieves the most relevant text from the document using vector similarity search and then generates an answer using Google's Gemini model.

---

## 🚀 Features

- Load PDF documents
- Extract text from PDF
- Split text into smaller chunks
- Generate embeddings using Hugging Face
- Store embeddings in FAISS Vector Database
- Retrieve relevant document chunks
- Generate answers using Google Gemini
- Simple and beginner-friendly implementation

---

## 🛠️ Technologies Used

- Python
- Google Colab
- LangChain
- Hugging Face Embeddings
- FAISS
- Google Gemini API
- PyPDF

---

## 📂 Project Workflow

```text
PDF Document
      │
      ▼
Load PDF
      │
      ▼
Split into Chunks
      │
      ▼
Generate Embeddings
      │
      ▼
Store in FAISS
      │
      ▼
User Question
      │
      ▼
Retrieve Relevant Chunks
      │
      ▼
Google Gemini
      │
      ▼
Generated Answer
```

---

## 📁 Project Structure

```
Document-Question-Answering-System/
│
├── Document_Question_Answering_System.ipynb
├── Ch13_ML_Implementation.pdf
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Document-Question-Answering-System.git
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

---

## ▶️ How to Run

1. Open the notebook in Google Colab.
2. Install the required libraries.
3. Upload the PDF document.
4. Add your Google Gemini API key.
5. Run all notebook cells.
6. Ask questions about the document.

---

## 💡 Sample Question

**Question**

```
Which machine learning algorithm is used?
```

**Answer**

```
The document uses a Decision Tree Classifier trained on the Iris dataset.
```

---

## 📚 Future Improvements

- Support multiple PDF documents
- Streamlit web interface
- Chat history
- Better chunking strategies
- Hybrid Search (Keyword + Vector Search)

---

## 👨‍💻 Author

**Sandeep Panigrahi**

B.Tech Computer Science Student

