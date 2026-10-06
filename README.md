# Micky 2.0

Micky 2.0 Phase 1 is a working foundation for a futuristic AI assistant. It includes a Python FastAPI backend, a React + TypeScript + Tailwind frontend, an AI-provider abstraction, profile storage, session-based conversation context, and a simplified circular "Micky Core" interface.

## Phase 1 scope

- Python AI backend
- FastAPI REST API
- Basic AI provider abstraction
- Session context management
- User profile management
- English, Hindi, Marathi, and Hinglish support
- Circular futuristic Micky UI
- Security-conscious environment configuration
- Test coverage for backend behavior

## Architecture

```text
MICKY UI
  React + TypeScript
      |
      | HTTP
      v
Python FastAPI
      |
      v
Micky Core
      |
   AI Brain / Profile / Context
      |
    AI Provider
```

## Stack

### Backend
- Python 3.11+
- FastAPI
- Pydantic
- Uvicorn
- python-dotenv

### Frontend
- React
- TypeScript
- Tailwind CSS
- Framer Motion

## Project structure

```text
micky/
├── backend/
│   ├── app/
│   │   ├── ai/
│   │   ├── api/
│   │   ├── core/
│   │   ├── micky/
│   │   ├── schemas/
│   │   └── main.py
│   ├── tests/
│   ├── .env.example
│   ├── README.md
│   ├── requirements.txt
│   └── .gitignore
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── vite.config.ts
│   ├── tailwind.config.js
│   └── README.md
└── README.md
```

## Installation

### Backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate  # Windows: 
cp .env.example .env
```

### Frontend

```bash
cd frontend
npm install
```

## Environment setup

Use the backend `.env.example` file as a template. Required variables:

```bash
MICKY_ENV=development
MICKY_API_KEY=
MICKY_PROVIDER=local
MICKY_ALLOWED_ORIGINS=http://localhost:5173
MICKY_LOG_LEVEL=INFO
MICKY_DEFAULT_LANGUAGE=en
```

## Backend startup

```bash
cd backend
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

## Frontend startup

```bash
cd frontend
npm run dev -- --host 0.0.0.0
```

## API endpoints

- `GET /api/health`
- `GET /api/profile`
- `PUT /api/profile`
- `POST /api/chat`

Example chat request:

```json
{
  "message": "Explain machine learning.",
  "conversation_id": "demo-1"
}
```

## Testing

Backend tests:

```bash
cd backend
pytest -q
```

Frontend build verification:

```bash
cd frontend
npm run build
```

## Troubleshooting

- Ensure Python dependencies are installed in the backend virtual environment.
- Ensure the frontend is using the backend URL on port 8000.
- If you see CORS issues, verify `MICKY_ALLOWED_ORIGINS` in `.env`.
- If your environment does not have Node or Python installed, install the required runtime first.

## Phase 2: Voice and speech interfaces

- Browser microphone control with simple permission handling
- Speech-to-text and text-to-speech provider abstractions
- Reuse the same Micky Core and conversation context for voice and text
- Local provider fallbacks for safe, offline voice flows

## Future roadmap

- Phase 3: Long-term memory
- Phase 4: AI tools and agent workflows
- Phase 5: Browser and computer automation
- Phase 6: Vision and OCR
- Phase 7: Full HUD and advanced interface

## Phase 1 completion status

This project is intentionally limited to the Phase 1 foundation for a future advanced AI assistant. It does not include voice, vision, memory, browser automation, or autonomous agents.
