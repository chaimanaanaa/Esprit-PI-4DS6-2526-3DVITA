# VitalAgent — 3D AI Medical Delegate Training Agent

A voice-enabled AI agent that trains medical delegates on pharmaceutical products.

Academic project in collaboration with **ESPRIT** and **Laboratoires Vital**. VITA Agent is an AI-powered 3D virtual assistant for pharmaceutical product training and sales support, combining Generative AI, Computer Vision and 3D technology.

## Screenshots

### Landing page — Meet VITA, your AI trainer
![Landing page](docs/images/landing-page.jpg)

### Training interface — talk with the 3D avatar
![Training interface](docs/images/training-interface.jpg)

## Features
- **RAG-based conversational AI** that answers pharmaceutical questions with contextual accuracy
- **Multilingual 3D avatar** with real-time lip synchronization
- **Real-time analytics dashboard** tracking delegate performance and learning progress
- **Reporting system** for interaction tracking, performance monitoring and continuous agent improvement
- **Personalized quizzes** adapted to each delegate's progress and weak areas
- **Interactive mind maps** turning complex product knowledge into visual summaries
- **Face recognition and engagement analysis** during evaluations

## Pipeline
Microphone → STT (Whisper large-v3) → RAG (ChromaDB + Ollama) → LLM → TTS → 3D Avatar

## Stack
| Layer | Technology |
|---|---|
| STT | Whisper large-v3 (free, local) |
| RAG | ChromaDB + nomic-embed-text |
| LLM | Ollama (Llama 3.1 70B) |
| TTS | edge-tts |
| Avatar | Three.js + TalkingHead (lip sync + body animation) |
| API | FastAPI (Python) + Spring Boot / Spring Security |
| DB | MySQL + ChromaDB |

## Setup

```bash
# 1. Clone the project and open its folder

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate       # Windows
source venv/bin/activate    # Mac/Linux

# 3. Install dependencies
pip install -r backend/requirements.txt

# 4. Configure environment
cp .env.example .env
# Edit .env with your MySQL credentials

# 5. Install and start Ollama
# Download: https://ollama.com/download
ollama pull llama3.1
ollama pull nomic-embed-text

# 6. Ingest your product data
python scripts/ingest.py

# 7. Start the API
python backend/main.py

# 8. Open frontend
# Open frontend/index.html in browser
```

## Team Structure
| Member | Module |
|---|---|
| - | `backend/rag/` — RAG pipeline (done) |
| - | `backend/stt/` — Whisper STT (done) |
| - | `backend/tts/` — Text to Speech |
| - | `frontend/avatar/` — 3D Avatar |
| - | `frontend/voice/` — Mic UI |

## Technologies
Python · FastAPI · Spring Boot · Spring Security · Llama 3.1 70B · Ollama · RAG · ChromaDB · Whisper (Speech-to-Text) · edge-tts (Text-to-Speech) · Three.js · TalkingHead · MySQL

## Git LFS (for 3D avatar files)
```bash
git lfs install
git lfs track "*.glb"
git lfs track "*.vrm"
```
