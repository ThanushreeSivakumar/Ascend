# Ascend — Architecture Overview

*A one-page reference for how data moves through the system. Update as real decisions replace assumptions.*

## 1. System at a Glance

```
┌─────────────┐      ┌──────────────┐      ┌───────────────────┐
│  Frontend   │ ───▶ │   Backend    │ ───▶ │   PostgreSQL DB    │
│ (Next.js)   │ ◀─── │  (FastAPI)   │ ◀─── │ users/domains/tasks│
└─────────────┘      └──────┬───────┘      └───────────────────┘
                             │
                 ┌───────────┼────────────┐
                 ▼                        ▼
         ┌───────────────┐       ┌──────────────────┐
         │  Claude API    │       │ External Data APIs│
         │ (Igris engine) │       │ jobs / hackathons  │
         └───────────────┘       │ / news / LinkedIn   │
                                  └──────────────────┘
```

## 2. Flow A — Domain Choice → Daily Task

1. User signs up and selects a **domain** (e.g. "Machine Learning") during onboarding.
2. Backend stores the domain on the `users` table and creates a `user_domain_profile` row (tracks skill level, focus areas, start date).
3. A daily scheduled job (cron / background worker) runs per active user:
   - Pulls the user's domain profile + task history (so Igris doesn't repeat itself).
   - Sends a structured prompt to the **Claude API**: domain, skill level, last N completed tasks, and any explicit user feedback.
   - Claude returns one concrete, scoped task (e.g. "Implement a logistic regression classifier from scratch on the Titanic dataset").
4. Task is stored in the `tasks` table (`status = pending`) and shown on the dashboard.
5. User marks it complete → status updates → next day's prompt includes this history for continuity.

**Key data model pieces:** `users`, `user_domain_profile`, `tasks` (id, user_id, domain, content, status, created_at, completed_at).

## 3. Flow B — Opportunity & Industry Intelligence

1. A separate scheduled job (runs less frequently, e.g. every 6–12h) queries external sources per domain:
   - Jobs/hackathons: a jobs API (e.g. Adzuna, RemoteOK) + a hackathon listing API (e.g. Devpost/MLH where available).
   - News/tech updates: a news API (e.g. NewsAPI) filtered by domain keywords.
   - LinkedIn: **flagged as high-risk** — LinkedIn's ToS restricts scraping and its official API access is limited/partner-gated. Treat this as a "research before building" item rather than an MVP dependency.
2. Raw results are filtered/deduped, tagged by domain, and stored in an `opportunities` table and a `news_items` table.
3. Frontend queries these tables (via backend endpoints) to populate the "Opportunities" and "Industry Intel" feed sections — this is read-only from the user's perspective, no LLM call needed at read time.
4. Optionally, Claude can be used offline to summarize/rank news items before storage, rather than at request time (keeps the feed fast and cheap).

**Key data model pieces:** `opportunities` (id, domain, type, title, url, source, fetched_at), `news_items` (id, domain, title, summary, url, source, fetched_at).

## 4. Why this split

- Keeping the **task-generation loop** (Flow A, real-time-ish, per-user) separate from the **aggregation loop** (Flow B, scheduled, shared across users) keeps LLM costs predictable and avoids hammering external APIs per user request.
- FastAPI was chosen because both flows are Python-friendly (LLM SDKs, data fetching/parsing), and Next.js keeps the frontend fast to iterate on with a large ecosystem.

## 5. Open Decisions

- Auth approach (email/password vs. OAuth) — not yet decided.
- Whether the daily task job runs via a simple cron (e.g. `APScheduler`) or a task queue (e.g. Celery/Redis) — start with cron for MVP, revisit at scale.
- LinkedIn data sourcing strategy — needs its own research spike before committing engineering time.
