# RAG Pipeline with Evals and Monitoring

A full-stack AI document Q&A system with a RAG pipeline, automated eval scoring, and real-time monitoring dashboard.

## Tech Stack
- **Frontend:** React, Tailwind CSS, Recharts
- **Backend:** FastAPI, SQLAlchemy, SSE
- **Database:** PostgreSQL + pgvector
- **AI:** Ollama (llama3.2), Sentence Transformers
- **Evals:** Ragas

## Features
- Upload PDFs and chat with them
- Semantic search using vector embeddings
- Streaming responses in real time
- Automated RAG quality scoring (faithfulness, relevance, precision)
- Monitoring dashboard with latency and quality metrics
- JWT authentication

## Project Structure
\```
rag-project/
├── backend/
│   ├── app/
│   │   ├── api/          # Route handlers
│   │   ├── core/         # Config and database
│   │   ├── models/       # Database models
│   │   └── services/     # Business logic
│   └── .env.example
└── frontend/
    └── src/
\```

## Setup Instructions

### Prerequisites
- Python 3.10+
- Node.js 18+
- PostgreSQL 15+
- Ollama

### Backend Setup
\```bash
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
\```

Create a `.env` file based on `.env.example`:
\```bash
cp .env.example .env
\```

Run the server:
\```bash
uvicorn app.main:app --reload
\```

### Frontend Setup
\```bash
cd frontend
npm install
npm start
\```

### AI Setup
\```bash
ollama pull llama3.2
ollama serve
\```

## Environment Variables
| Variable | Description |
|---|---|
| `DATABASE_URL` | PostgreSQL connection string |
| `SECRET_KEY` | JWT secret key |
| `OLLAMA_BASE_URL` | Ollama server URL |
| `LLM_MODEL` | LLM model name |
| `EMBEDDING_MODEL` | Embedding model name |