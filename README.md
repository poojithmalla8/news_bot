# News Bot 📰

A daily morning news briefing, delivered to WhatsApp and email before Malla wakes up.

## What it does

Every morning, a scheduled job researches the day's news and sends a structured briefing covering:

| # | Section | Detail |
|---|---------|--------|
| 1 | 🇺🇸 US News (10–20 items) | Top stories, elections, new bills passed, anything affecting H1B visa holders |
| 2 | 📈 Economics & Markets | How the market is doing: S&P 500, Nasdaq, Dow, key movers, Fed/economic headlines |
| 3 | 🏏⚽ Sports | Cricket and football headlines |
| 4 | 🌤 Weather | Forecast for current location (zip 95134 — San Jose, CA) |
| 5 | 🌍 World Politics (5–10 items) | Top global political stories |
| 6 | ⚠️ Natural Calamities | Disasters and severe events across the world |
| 7 | 🇮🇳 India News (15–20 items) | Politics, stocks, IPOs, and other top stories |

## Delivery

- **WhatsApp:** brief summary delivered to the linked WhatsApp chat with Muse
- **Email:** full briefing sent via Gmail to the user's address

## How it runs

The briefing is produced by a scheduled job (cron) in the Muse runtime that runs each morning at wake-up time. The job:

1. Researches each section with current news sources (news vertical search, market data, weather).
2. Composes the briefing following `briefing-spec.md`.
3. Sends the full briefing by email.
4. Delivers the summary to WhatsApp.

The job definition lives in `cron-job.md`. This repo holds the spec and docs; the
scheduler itself lives in the Muse runtime (see setup status below).

## Setup status

- [ ] Gmail connected (for email sending)
- [ ] WhatsApp linked (for WhatsApp delivery)
- [ ] Daily cron job created
- [ ] Wake-up time confirmed

## Files

- `briefing-spec.md` — exact sections, order, and formatting of the daily brief
- `cron-job.md` — the scheduled job definition/instructions
- `README.md` — this file
