# GEMINI-CHAT-API
FastAPI + Google Gemini multi-turn chat API with session support

# Gemini Chat API ✨

**FastAPI** + **Google Gemini 1.5 Flash** → Lightweight **multi-turn** conversational API with session support

A clean, fast and production-ready backend for building chatbots, AI assistants or any Gemini-powered conversation feature.

## Why this project? 🤔

I wanted a **simple yet powerful** starter template to:
- Use Gemini in real web/mobile applications
- Keep full conversation context (multi-turn)
- Deploy quickly (Docker + Railway/Render ready)
- Have clean, modular code that's easy to extend

Perfect for → chat widgets, Telegram/Discord bots, internal tools, prototypes, learning FastAPI + LLM integration

## ✨ Features

- Multi-turn conversations with persistent context
- Automatic session creation (`session_id`)
- View / Delete chat history
- CORS enabled (frontend-ready)
- Clean modular structure
- Auto-generated interactive docs (Swagger)
- Logging + Error handling
- Docker support 🐳
- Ready for Redis/DB upgrade in future

## 🛠 Tech Stack

- **Framework**: FastAPI 0.115+
- **AI**: Google Generative AI (gemini-1.5-flash)
- **Validation**: Pydantic v2
- **Env**: python-dotenv
- **Server**: Uvicorn
- **CORS**: FastAPI middleware
- **Session**: In-memory (easy to swap with Redis)

## 🚀 Quick Start

```bash
# 1. Clone
git clone https://github.com/YOUR_USERNAME/gemini-chat-api.git
cd gemini-chat-api

# 2. Virtual environment
python -m venv venv
source venv/bin/activate         # Windows → venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Environment
cp .env.example .env
# → Open .env and add your key:
# GOOGLE_API_KEY=your-real-key-here

# 5. Run 🔥
uvicorn app.main:app --reload --port 8000


Method,Endpoint,Description,Params / Body
GET,/,Health check,—
POST,/api/chat,Send message (new or continue session),"Body: {""user_message"": ""...""} + ?session_id=xxx (optional)"
GET,/api/chat/history,Get full conversation history,?session_id=xxx (required)
DELETE,/api/chat/session,Delete session & history,?session_id=xxx (required)

curl -X POST "http://localhost:8000/api/chat" \
  -H "Content-Type: application/json" \
  -d '{"user_message": "Hi! Tell me a fun fact 🌟"}'

docker build -t gemini-chat-api .
docker run -p 8000:8000 --env-file .env gemini-chat-api

Redis / PostgreSQL for session persistence
API Key / JWT authentication
Rate limiting (slowapi)
Response streaming
File upload support (images, pdf → Gemini vision)
WebSocket endpoint

Author Name - SUMIT PANDEY



