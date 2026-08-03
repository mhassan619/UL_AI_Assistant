# 🤖 UL AI Assistant — University of Layyah Chatbot

<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/mhassan619/UL_AI_Assistant)
[![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)](https://github.com/mhassan619/UL_AI_Assistant)
[![Groq](https://img.shields.io/badge/Groq_API-F55036?style=for-the-badge)](https://github.com/mhassan619/UL_AI_Assistant)
[![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://github.com/mhassan619/UL_AI_Assistant)
[![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://ul-ai-assistant.vercel.app/)

**[🔗 Live App → ul-ai-assistant.vercel.app](https://ul-ai-assistant.vercel.app/)**

</div>

---

## 📌 What Is This?

**UL AI Assistant** is an AI-powered Help Desk Chatbot for the **University of Layyah**, built using a **RAG (Retrieval-Augmented Generation)** pipeline. Students can ask any question about admissions, departments, faculty, or campus life — and get instant, accurate answers in both **English and Roman Urdu**.

---

## 🧠 Problem → Solution

**Problem:** Students at University of Layyah had no instant way to get answers about admissions, fee structure, departments, and campus information. They had to call offices or search through outdated pages.

**Solution:** Built a RAG chatbot that indexes all university data into a vector store. When a student asks a question, relevant information is retrieved and passed to Llama 3.1 (via Groq API) to generate a precise, grounded answer — eliminating hallucinations from general LLM knowledge.

---

## ⚙️ How It Works

```
User Question
      ↓
RAG Engine (rag_engine.py)
      ↓
Keyword-based Retrieval from vector_db/
      ↓
Relevant chunks → Groq API (Llama 3.1 8B Instant)
      ↓
Grounded Answer → Flask API → User
```

1. University data stored in `data/university_data.txt` as structured sections
2. `ingest.py` processes and indexes the data into `vector_db/`
3. `rag_engine.py` retrieves relevant chunks using keyword matching
4. Groq API (Llama 3.1 8B) generates accurate, context-aware answers
5. Flask serves the chatbot via clean REST API (`/chat` endpoint)
6. Deployed on Vercel — live and publicly accessible

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **LLM** | Llama 3.1 8B Instant via Groq API |
| **RAG Framework** | LangChain |
| **Backend** | Flask (Python) |
| **Vector Store** | Custom keyword-based retrieval (vector_db/) |
| **Frontend** | HTML · CSS · JavaScript |
| **Deployment** | Vercel |

---

## 📂 Project Structure

```
UL_AI_Assistant/
├── app.py              # Flask backend — REST API & /chat endpoint
├── rag_engine.py       # RAG pipeline — retrieval + LLM generation
├── ingest.py           # Data ingestion & vector_db indexing
├── requirements.txt    # Python dependencies
├── vercel.json         # Vercel deployment config
├── data/
│   └── university_data.txt   # University information (structured)
├── vector_db/          # Indexed knowledge base
├── templates/          # HTML frontend templates
└── static/             # CSS & JavaScript files
```

---

## 💡 Key Features

- ✅ Answers university queries instantly — admissions, departments, faculty, fees
- ✅ Responds in both **English and Roman Urdu**
- ✅ Strict fallback when information is unavailable — no hallucinations
- ✅ Fast response using Groq's Llama 3.1 8B Instant model
- ✅ Clean REST API architecture — `/chat` endpoint
- ✅ Deployed live on Vercel — zero downtime

---

## 🚀 Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/mhassan619/UL_AI_Assistant.git
cd UL_AI_Assistant

# 2. Install dependencies
pip install -r requirements.txt

# 3. Set your Groq API key
# Create a .env file and add:
# GROQ_API_KEY=your_groq_api_key_here

# 4. Index the data
python ingest.py

# 5. Run the app
python app.py
```

---

## 🌐 Live Demo

👉 **[ul-ai-assistant.vercel.app](https://ul-ai-assistant.vercel.app/)**

Try asking:
- "What are the admission requirements?"
- "Computer Science department mein kya courses hain?"
- "Fee structure kya hai?"

---

<div align="center">

Built by **[Muhammad Hassan](https://github.com/mhassan619)** · [LinkedIn](https://www.linkedin.com/in/muhammad-hassan-python)

</div>
