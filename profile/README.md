<div align="center">

<img src="./assets/logo.png" alt="Marketing Command Centre logo" width="140" />

# CommandCentre

**Turn Discord into a project management tool.**

A self-hosted, Jira-lite platform that runs project management where your team already talks: Discord. Capture requests, track them through a status workflow, keep a full audit trail, and watch deadlines on a live dashboard.

</div>

---

## 👋 What is this?

Marketing Command Centre is a small suite of connected services that manage the lifecycle of a work item — think tickets, tasks, or requests — without forcing your team into yet another app:

1. A **Discord bot** is the front door: create, assign, and update items with slash commands, right inside Discord.
2. A **Spring Boot backend** stores items, moves them through a status workflow, and keeps a full audit trail.
3. A **web dashboard** visualises deadlines and status on an interactive calendar/board so nothing slips.

Everything talks over a shared REST API, so the pieces can run together or be swapped out individually.

> **One of many use cases:** it started life running the [UTMMSA](https://github.com/MarketingCommandCentre) marketing team's content pipeline — but the workflow is generic, so it fits any team that lives in Discord.

## 📦 Repositories

| Repository | What it does | Stack |
| --- | --- | --- |
| **[backend](https://github.com/MarketingCommandCentre/backend)** | Spring Boot microservice for item management and audit events. Discord OAuth + JWT auth, automatic audit logging, RESTful JSON API. | Java 21 · Spring Boot 3.5 · SQLite · JPA |
| **[discord-bot](https://github.com/MarketingCommandCentre/discord-bot)** | Discord bot that lets a team create, assign, and update work items from inside Discord and syncs them to the backend. | Python · discord.py |
| **[dashboard](https://github.com/MarketingCommandCentre/dashboard)** | Interactive calendar + status board for tracking deadlines, with light/dark mode and a CSV fallback when the API is offline. | JavaScript · Vite · FullCalendar |

## 🏗️ How it fits together

```
┌──────────────┐     requests      ┌──────────────┐     events      ┌──────────────┐
│  discord-bot │ ───────────────▶  │   backend    │ ◀────────────── │  dashboard   │
│  (Python)    │   REST / JWT      │ (Spring Boot)│   REST / JWT    │ (JS + Vite)  │
└──────────────┘                   └──────┬───────┘                 └──────────────┘
                                          │
                                    ┌─────▼─────┐
                                    │  SQLite   │  requests + audit events
                                    └───────────┘
```

- **Items** flow in from Discord and out to the dashboard calendar/board.
- **Audit events** are logged automatically on every create / update / delete.
- **Auth** is handled with Discord OAuth for users and long-lived JWTs for the bot.

## 🚀 Getting started

Each repository has its own setup guide in its README. A typical local stack looks like:

```bash
# 1. Backend (http://localhost:8080)
cd backend
./mvnw spring-boot:run

# 2. Discord bot
cd discord-bot
pip install -r requirements.txt
python main.py          # requires DISCORD_TOKEN in .env

# 3. Dashboard
cd dashboard
npm install
npm run dev             # point config.js at the backend URL
```

## 🤝 Contributing

Issues and pull requests are welcome on each repository. Please open an issue to discuss larger changes before starting work.

---

<div align="center">

Built with ❤️ for UTMMSA by [@ibratech04](https://github.com/ibratech04) 

</div>
