<div align="center">

<img src="./assets/logo.png" alt="Marketing Command Centre logo" width="140" />

# CommandCentre

**Turn Discord into a project management tool.**

A self-hosted, "Jira-lite"-esque platform that runs project management where your team already talks: Discord. Capture tickets, watch them flow through statuses, keep a full audit trail, and watch deadlines on a live dashboard!

</div>

---

## 👋 What is this?

Marketing Command Centre is a small suite of connected services that manage the lifecycle of a work item — think tickets, tasks, or requests *without* forcing your team into yet another app:

1. A **Discord bot** maintains the workflow, allowing users to create items, move them through statuses, and view deadlines without leaving Discord.
2. A **Spring Boot backend** orchestrates the workflow, storing items and their audit trail, and handles authentication and authorization.
3. A **web dashboard** visualizes deadlines and status on an interactive calendar/board so nothing slips.

Everything talks over a shared REST API, so the pieces can run together or be swapped out individually.

> **One of many use cases:** it started life running the [UTMMSA](https://github.com/MarketingCommandCentre) marketing team's content pipeline — but the workflow is generic, so it fits any team that lives in Discord.

## Repositories

| Repository | What it does | Stack |
| --- | --- | --- |
| **[backend](https://github.com/MarketingCommandCentre/backend)** | Spring Boot microservice handling all backend tasks | Spring Boot |
| **[discord-bot](https://github.com/MarketingCommandCentre/discord-bot)** | Discord client wrapping the microservice, providing the main Discord UI| discord.py |
| **[dashboard](https://github.com/MarketingCommandCentre/dashboard)** | Interactive calendar + status board for tracking deadlines| React.js |

## System Architecture

```
┌──────────────┐     requests      ┌──────────────┐     events      ┌──────────────┐
│  discord-bot │ ───────────────▶  |   backend   │ ◀────────────── │  dashboard   │
│  (Python)    │   REST / JWT      │ (Spring Boot)│   REST / JWT    │ (JS + Vite)  │
└──────────────┘                   └──────┬───────┘                 └──────────────┘
                                          │
                                    ┌─────▼─────┐
                                    │ SQLite/Postgres   │  requests + audit events
                                    └───────────┘
```

- **Items** flow in from Discord and out to the dashboard calendar/board.
- **Audit events** are logged automatically on every create / update / delete.
- **Auth** is handled with Discord OAuth for users and long-lived JWTs for the bot.

## Next Steps

The ultimate goal of this project is to turn it into a "Guidewire" of sorts for project management; Provide users with a extensive, powerful core which handles 99% of business needs, and allow more advanced users to extend the platform with their own custom workflows, dashboards, and integrations.

Doing so requires the backend to be completely refactored, and requires the creation of two consumer libraries for the backend API: one for Python and one for TypeScript. These libraries will allow developers to consume the backend API in a more idiomatic way, and will make it easier to build custom workflows and expand upon the platform.


<div align="center">

Built with ❤️ by [@ibratech04](https://github.com/ibratech04)

</div>
