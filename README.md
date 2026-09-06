# 🚀 Ascend

<p align="center">
  <h1 align="center">Ascend</h1>
  <p align="center"><strong>Your AI Mentor for Lifelong Growth</strong></p>
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#meet-igris">Meet Igris</a> •
  <a href="#key-features">Key Features</a> •
  <a href="#how-it-works">How It Works</a> •
  <a href="#mcp-integration">MCP Integration</a> •
  <a href="#tech-stack">Tech Stack</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#roadmap">Roadmap</a> •
  <a href="#license">License</a>
</p>

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Status](https://img.shields.io/badge/status-in%20development-yellow.svg)](#)
[![Made with](https://img.shields.io/badge/made%20with-%E2%9D%A4%EF%B8%8F-red.svg)](#)

---

## Overview

**Ascend** is an AI-powered personalized learning and career development platform. Unlike traditional platforms that dump generic courses and links, Ascend gives every user a dedicated AI mentor — **Igris** — that understands their goals, tracks progress, identifies weaknesses, and continuously adapts the learning journey.

Most career growth advice is generic, static, and disconnected from what's happening in an industry right now. Ascend fixes that by pairing users with an intelligent mentor who builds a comprehensive, hands-on roadmap around a single domain — such as Machine Learning, Product Design, DevOps, or Finance.

> **The Problem:** Learners drown in information overload, conflicting resources, and lack of direction. Most people don't fail from lack of intelligence — they fail from lack of guidance.
>
> **The Solution:** A single intelligent mentor that actively plans, teaches, evaluates, and evolves with you.

---

## Meet Igris

Igris is the core intelligence behind Ascend — a disciplined mentor, not a generic chatbot.

Instead of *"Here are ten resources"*, Igris says:
> *"Based on your progress, these two resources will help you the most today."*

Instead of *"What would you like to learn?"*, Igris asks:
> *"Your goal is becoming a Machine Learning Engineer in six months. Shall we continue today's roadmap?"*

Igris remembers what you've completed, identifies recurring mistakes, recommends the right resources at the right time, and continuously adjusts your roadmap based on real progress.

---

## Key Features

### 🗺️ Personalized Roadmaps
Dynamic learning paths built from your goals, skill level, available time, and learning preferences — not static course lists.

### 📋 Daily Missions
Each day, Igris prioritizes high-impact activities: reading docs, coding exercises, project building, interview prep, and concept reviews — scaled to your available time.

### 📚 Smart Resource Discovery
Curated recommendations across books, docs, videos, research papers, GitHub repos, podcasts, courses, and more — each with an explanation of *why* it fits your current stage.

### 🎯 Personalized Domain Mastery
Ascend goes deep on one chosen career field at a time. Every recommendation, task, and resource is tailored specifically to that domain.

### 📅 Daily Actionable Tasks
Every day, Igris delivers one custom task designed to build practical, real-world skill.

### 🔍 Curated Opportunities
Ascend surfaces relevant hackathons, open job listings, and networking avenues filtered for the user's chosen focus area.

### 📊 Continuous Assessment
Skill evaluation through quizzes, coding challenges, project reviews, and practical exercises. Weak areas are automatically identified and addressed.

### 🔄 Intelligent Adaptation
If motivation dips, plans become lighter. If you demonstrate mastery, harder material appears. Repeated mistakes trigger targeted revision. The platform grows with you.

### 💼 Career Guidance
Resume building, portfolio development, GitHub/LinkedIn optimization, personal branding, interview prep, and networking strategies — all tailored to your domain.

### 📡 Industry Intelligence
Igris aggregates trending LinkedIn discussions, relevant news articles, and technology updates so users stay ahead of market shifts.

### 🌐 Industry Awareness
Stay current with emerging technologies, research breakthroughs, trending tools, framework releases, and community discussions — without monitoring dozens of sites.

### 📈 Progress Tracking
Visualize completed milestones, skill growth, learning streaks, time invested, project completion, and career readiness in a dynamic profile.

---

## How It Works

1. **Tell Igris your goals** — domain, experience level, career objective, timeline, and daily availability.
2. **Receive a custom roadmap** — broken into milestones with curated resources, hands-on projects, quizzes, and evaluations.
3. **Learn daily** — Igris assigns focused, high-impact tasks each day.
4. **Get assessed continuously** — understanding is measured through practice, not just completion checkboxes.
5. **Adapt and evolve** — the roadmap reshapes itself based on your real progress.

---

## MCP Integration

Ascend leverages the **Model Context Protocol (MCP)** to connect with external tools, giving Igris visibility into your broader learning ecosystem:

| Integration | Purpose |
|---|---|
| **GitHub** | Repository analysis & contribution tracking |
| **Google Drive** | Study material organization |
| **Gmail** | Internship & interview email detection |
| **Calendar** | Intelligent study scheduling |
| **YouTube** | Learning history & curated recommendations |
| **Notion** | Note synchronization |
| **Browser Tools** | Documentation & research |
| **File System** | Project & source code analysis |

---

## 🛠️ Tech Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js (React) + Tailwind CSS |
| Backend | Python (FastAPI) |
| AI / LLM | Claude API (Anthropic) — powers Igris's task generation & conversation |
| Database | PostgreSQL |
| Deployment | Vercel (frontend) + Render/Railway (backend + DB) |

> These are proposed defaults for the MVP, not locked-in decisions — see [ARCHITECTURE.md](./ARCHITECTURE.md) for the reasoning.

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

Contributions, issues, and feature requests are welcome! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## Philosophy

> **Knowledge alone is not enough. Consistent guidance creates mastery.**

Information is everywhere. Mentorship is rare. Ascend bridges that gap — giving every learner an intelligent mentor that remembers, adapts, teaches, and grows with them.

Learning should feel like climbing a mountain with someone who already knows the path.

That guide is **Igris**. That journey is **Ascend**.

---

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.

Distributed under the MIT License. See `LICENSE` for more information.

---

**Ascend** — because growth shouldn't be generic.
