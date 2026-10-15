# BhashaSathi 🗣️

**A Language-Agnostic Campus Assistant**

Smart India Hackathon 2025 · Problem Statement 25104 · Theme: Smart Education · Team BhashaBot

> *BhashaSathi speaks every language so you don't have to.*

## The Problem

Campus offices field the same questions all day: when are fees due, how do I apply for a scholarship, has the timetable changed. Queues build up, staff time goes to repetitive answers, and the information that does exist is buried in circular PDFs and notice boards.

The gap widens for students who are most comfortable in Hindi or a regional language. Information that is technically available is not actually accessible.

## The Solution

BhashaSathi is a multilingual conversational assistant for college campuses. It answers common queries in English, Hindi, and several regional languages, understanding what a student means rather than matching keywords.

Unlike a static FAQ page, it maintains context across a multi-turn conversation — a student can ask a follow-up without repeating themselves — and hands off to a human when a query goes beyond what it should answer on its own.

## ✨ Key Features

- **Multilingual support** — English, Hindi, and regional languages
- **Context-aware conversations** — retains context across multiple turns
- **Retrieval-grounded answers** — responses drawn from actual campus documents, not model guesswork
- **Human fallback** — complex or sensitive queries escalate to staff
- **Conversation logs** — daily logs let student volunteers refine responses over time
- **Privacy-first** — no leakage of student data
- **Plug-and-play** — works through Telegram or embedded in the college website

## 🏗️ Tech Stack

**Core**
- Python

**AI / Retrieval**
- LangChain — orchestration of LLM workflows
- FAISS — vector store for similarity search
- Sentence Transformers (Hugging Face) — embedding generation
- Sarvam AI API — multilingual chat LLM

**API**
- FastAPI — REST API framework

**Interfaces**
- Telegram Bot API — conversational access
- HTML, CSS, JavaScript — web interface

**Hosting**
- AWS Cloud(Future Scope)

## 🔎 How It Works

1. Campus information (fee schedules, scholarship rules, timetables) is chunked and embedded using Sentence Transformers.
2. Embeddings are indexed in FAISS for fast similarity search.
3. A student query — in any supported language — is embedded and matched against the index.
4. Retrieved context is passed to the Sarvam AI LLM through LangChain, which generates a grounded, conversational answer in the student's own language.
5. Conversation history is retained so follow-up questions resolve correctly.
6. Low-confidence or out-of-scope queries route to a human.

## 📂 Project Structure

```
SIH25PROJ
│
├── sih.py             # Core backend logic and API
├── telegram_bot.py    # Telegram interface
├── sih.html           # Web interface
├── sih.css
├── sih.js
└── requirements.txt
```

## 🚀 Getting Started

```bash
git clone https://github.com/manyashri1901/SIH25PROJ.git
cd SIH25PROJ

pip install -r requirements.txt
```

Create a `.env` file in the project root:

```
SARVAM_API_KEY=your_sarvam_api_key
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
```

Run the services:

```bash
# start the API
python sih.py

# start the Telegram bot (in a second terminal)
python telegram_bot.py
```

## 📊 Intended Impact

- Handles a large share of repetitive queries, freeing staff for cases that need judgement
- Provides 24/7 access to authoritative information
- Remains student-maintainable — volunteers refine responses from conversation logs
- Closes the language gap with culturally inclusive access

## ⚠️ Known Challenges

- Translation accuracy and context retention vary across Indian languages
- Scaling to thousands of concurrent users requires load balancing and cloud hosting
- Student data requires encryption and strict access controls

## 👥 Team

Team BhashaBot — Smart India Hackathon 2025

## Author

Manya Shrivastava
