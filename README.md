# Video Competitor Intelligence & Automated Report Generator

[![Live Deployment](https://img.shields.io/badge/Live-On%20Render-10B981?style=for-the-badge&logo=render&logoColor=white)](https://video-competitor-intelligence-and-report-ykwa.onrender.com/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI & Flask](https://img.shields.io/badge/Framework-Flask%20%2F%20SSE-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Gemini & Groq](https://img.shields.io/badge/LLM-Gemini%202.0%20%7C%20LLaMA%203.3-8B5CF6?style=for-the-badge)](https://groq.com/)

An automated market research and competitor intelligence pipeline that ingests YouTube channels, analyzes transcripts and video engagement metrics across multiple LLMs, and compiles an executive **11-slide PowerPoint presentation (.pptx)** in under 5 minutes.

---

## 🏗️ System Architecture & Multi-Model Pipeline

```
[User Search Query]
       │
       ▼
[YouTube Data API v3] ─── (Rotates across 4 API keys to prevent quota exhaustion)
       │
       ▼
[Caption & Metadata Extraction] ─── (Grounded transcript ingestion)
       │
       ▼
[Gemini 2.0 Flash] ─── (Extracts strategic positioning & thematic trends)
       │
       ▼
[Groq / LLaMA 3.3 70B] ─── (Drafts executive slides & actionable recommendations)
       │
       ▼
[LLaMA 3.1 8B Guard Gate] ─── (Autonomous evaluation gate: flags hallucinated facts)
       │
       ▼
[python-pptx Engine] ─── (Builds 11-slide styled deck & streams progress via SSE)
```

---

## ✨ Key Features

- **Multi-Model LLM Ensemble**:
  - **Gemini 2.0 Flash**: High-speed reasoning over dense video transcripts.
  - **Groq / LLaMA 3.3 70B**: Structured synthesis and narrative generation.
  - **LLaMA 3.1 8B Quality Gate**: Evaluates slide content for consistency before final assembly.
- **Quota-Resilient Data Ingestion**:
  - Implements automatic round-robin rotation across 4 YouTube Data API keys.
- **Real-Time Streaming**:
  - Live progress updates streamed to the frontend via **Server-Sent Events (SSE)**.
- **Automated PowerPoint Generation**:
  - Custom `python-pptx` builder formatting layout, charts, bullet points, and speaker notes.

---

## 🚀 Quickstart

```bash
# 1. Clone repository
git clone https://github.com/Gokulkrishnar10/Video-Competitor-Intelligence-and-Report-Generator.git
cd Video-Competitor-Intelligence-and-Report-Generator

# 2. Install dependencies
pip install -r requirements.txt

# 3. Configure environment variables (.env)
cp .env.example .env
# Set GEMINI_API_KEY, GROQ_API_KEY, and YOUTUBE_API_KEYS

# 4. Run application
python app.py
```

