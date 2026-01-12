# ZYNEXA ✨
FastAPI + Google Gemini multi-turn chat API with session support

## ZYNEXA Chat API 🚀

**FastAPI** + **Google Gemini 1.5 Flash** → A lightweight, **multi-turn**
conversational AI API with persistent session-based memory.

**ZYNEXA** is a clean, fast, and production-ready backend for building
chatbots, AI assistants, and Gemini-powered conversational applications.

---

## Why ZYNEXA? 🤔

ZYNEXA was built as a **simple yet powerful** starter template to:

- Use Google Gemini in real-world web & mobile applications
- Maintain full conversation context (multi-turn memory)
- Deploy quickly (Docker + Railway / Render ready)
- Follow clean, modular, and scalable backend architecture

Perfect for →
chat widgets, Telegram / Discord bots, internal tools, prototypes,
and learning FastAPI + LLM integration.

---

## ✨ Features

- Multi-turn conversations with persistent context
- Automatic session creation (`session_id`)
- View / delete conversation history
- CORS enabled (frontend-ready)
- Clean & modular project structure
- Auto-generated interactive API docs (Swagger)
- Logging & error handling
- Docker support 🐳
- Ready for Redis / database upgrade in future

---

## 🛠 Tech Stack

- **Framework**: FastAPI 0.115+
- **AI Model**: Google Generative AI (gemini-1.5-flash)
- **Validation**: Pydantic v2
- **Environment**: python-dotenv
- **Server**: Uvicorn
- **CORS**: FastAPI middleware
- **Session Storage**: In-memory (easy to swap with Redis)

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/zynexa-chat-api.git
cd zynexa-chat-api

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate          # Windows → venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Environment variables
cp .env.example .env
# Open .env and add:
# GOOGLE_API_KEY=your-real-key-here

# 5. Run the server 🔥
uvicorn app.main:app --reload --port 8000

| Method | Endpoint            | Description                            | Params / Body                                                    |
| ------ | ------------------- | -------------------------------------- | ---------------------------------------------------------------- |
| GET    | `/`                 | Health check                           | —                                                                |
| POST   | `/api/chat`         | Send message (new or existing session) | Body: `{ "user_message": "..." }` + `?session_id=xxx` (optional) |
| GET    | `/api/chat/history` | Get full conversation history          | `?session_id=xxx` (required)                                     |
| DELETE | `/api/chat/session` | Delete session & history               | `?session_id=xxx` (required)                                     |

curl -X POST "http://localhost:8000/api/chat" \
  -H "Content-Type: application/json" \
  -d '{"user_message": "Hi! Tell me a fun fact 🌟"}'

docker build -t zynexa-chat-api .
docker run -p 8000:8000 --env-file .env zynexa-chat-api

🔮 Future Enhancements

Redis / PostgreSQL for session persistence

API Key / JWT authentication

Rate limiting (slowapi)

Response streaming

File upload support (images, PDFs → Gemini Vision)

WebSocket-based real-time chat

Author - Sumit Pandey



