# 🎓 UL AI Assistant — University of Layyah Chatbot

An AI-powered Help Desk Chatbot for the University of Layyah, built with RAG 
(Retrieval-Augmented Generation) architecture using LangChain, Groq API (Llama 3.1), 
and Flask. Deployed live on Vercel.

## 🔗 Live Demo
👉 [ul-ai-assistant.vercel.app](https://ul-ai-assistant.vercel.app/)

## ⚙️ How It Works
1. University data is stored in `data/university_data.txt` as structured sections
2. `ingest.py` processes and indexes the data into `vector_db/`
3. `rag_engine.py` retrieves relevant sections using keyword matching
4. Groq API (Llama 3.1 8B) generates accurate, context-aware answers
5. Flask serves the chatbot via a clean REST API (`/chat` endpoint)

## 🛠️ Tech Stack
- **Backend:** Python, Flask
- **AI/LLM:** LangChain, Groq API, Llama 3.1 8B Instant
- **RAG Pipeline:** Custom keyword-based retrieval + LLM generation
- **Deployment:** Vercel
- **Frontend:** HTML, CSS, JavaScript

## 🚀 Run Locally
```bash
git clone https://github.com/mhassan619/UL_AI_Assistant.git
cd UL_AI_Assistant
pip install -r requirements.txt
# Add your GROQ_API_KEY in environment
python app.py
```

## 💡 Features
- Answers university queries in both English and Roman Urdu
- Strict fallback when information is unavailable
- Fast response using Groq's Llama 3.1 8B Instant model
- Clean REST API architecture