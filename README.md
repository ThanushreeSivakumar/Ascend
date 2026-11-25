# 🚀 Ascend

### Bridging the gap between where you are and where you want to be.

**An AI-powered career mentorship platform that turns aspirations into a daily, executable roadmap.**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Status](https://img.shields.io/badge/status-in%20development-yellow.svg)](#)
[![Made with](https://img.shields.io/badge/made%20with-%E2%9D%A4%EF%B8%8F-red.svg)](#)

---

## 🧭 Overview

Most career growth advice is generic, static, and disconnected from what's actually happening in an industry *right now*. **Ascend** fixes that.

Ascend pairs every user with **Igris** — an intelligent AI mentor — who takes a single, targeted domain (e.g. Machine Learning, Product Design, DevOps, Finance) and builds a **comprehensive, hands-on roadmap to mastery** around it. Instead of a one-size-fits-all course, users get a living, adapting mentorship system that reacts to the market as fast as the market moves.

---

## ✨ Core Features

### 🎯 Personalized Domain Mastery
Ascend doesn't try to teach everything — it goes deep on **one chosen career field** at a time. Every recommendation, task, and resource is tailored specifically to that domain.

### 📅 Daily Actionable Tasks
Every day, Igris delivers **one custom task** designed to build practical, real-world skill.

### 🔍 Curated Opportunities
Ascend surfaces relevant **hackathons**, open **job listings**, and **networking** avenues — filtered for the user's chosen focus area.

### 📡 Industry Intelligence
Igris aggregates trending **LinkedIn discussions**, relevant **news articles**, and **technology updates** so users stay ahead of market shifts.

---

## 🛠️ Tech Stack

| Layer      | Technology |
| ---------- | ---------- |
| Frontend   | Next.js (React) + Tailwind CSS |
| Backend    | Python (FastAPI) |
| AI / LLM   | Claude API (Anthropic) — powers Igris's task generation & conversation |
| Database   | PostgreSQL |
| Deployment | Vercel (frontend) + Render/Railway (backend + DB) |

> These are proposed defaults for the MVP, not locked-in decisions — see [`ARCHITECTURE.md`](./ARCHITECTURE.md) for the reasoning.

---

## 📦 Getting Started

### Prerequisites

- Node.js 18+ and npm/pnpm (frontend)
- Python 3.11+ and pip (backend)
- PostgreSQL 14+ (local instance or hosted, e.g. Supabase/Railway)
- An Anthropic API key (for Igris)

### Installation

```bash
git clone https://github.com/Thanushree-Sivakumar/Ascend.git
cd Ascend

# Backend
cd backend
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # fill in DATABASE_URL, ANTHROPIC_API_KEY, etc.

# Frontend
cd ../frontend
npm install
cp .env.example .env.local   # fill in NEXT_PUBLIC_API_URL
```

### Running Locally

```bash
# Terminal 1 — backend
cd backend
uvicorn app.main:app --reload --port 8000

# Terminal 2 — frontend
cd frontend
npm run dev
```

The app will be available at `http://localhost:3000`, talking to the API at `http://localhost:8000`.
---

## 🗺️ Roadmap

- [ ] MVP: Domain selection + daily task generation
- [ ] Igris conversational mentor interface
- [ ] Opportunity aggregation (hackathons, jobs, networking)
- [ ] Industry intelligence feed (LinkedIn, news, tech trends)
- [ ] Progress tracking & analytics dashboard
- [ ] Mobile app

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for guidelines.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

**Ascend** — because growth shouldn't be generic.
