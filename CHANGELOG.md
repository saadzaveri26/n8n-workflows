# 📅 Changelog

All workflows added to this repo, tracked by date.

---

## 2026-07-06 — Website Monitor Agent
**Category:** ai-agents
**Complexity:** Intermediate
**Description:** Scheduled daily agent that fetches any website, compares content with previously stored version using n8n static data, and sends AI-powered change analysis to Telegram when differences are detected. No external database needed.

## 2026-07-05 — GitHub Activity Digest
**Category:** data-pipelines
**Complexity:** Intermediate
**Description:** Scheduled evening workflow that fetches GitHub profile stats and recent public events via GitHub API, aggregates today's activity, generates a motivational summary using Groq, and delivers it to Telegram daily at 6PM.

## 2026-07-04 — AI Job Application Tracker
**Category:** productivity
**Complexity:** Intermediate
**Description:** Telegram bot that uses Groq LLaMA3 to parse natural language job application messages, extract company, role, status and source, then logs everything to Google Sheets automatically.

## 2026-07-03 — Smart Expense Logger Bot
**Category:** telegram-bots
**Complexity:** Beginner
**Description:** Telegram bot that parses natural language expense messages like "Coffee 150 food" and automatically logs item, amount, category, date and time to Google Sheets. Uses OAuth2 for Google Sheets authentication.

## 2026-07-02 — arXiv ML Paper Daily Digest
**Category:** telegram-bots
**Complexity:** Beginner-Intermediate
**Description:** Scheduled daily workflow that fetches the 5 latest ML/AI papers from arXiv, summarizes each abstract using Groq LLaMA3, and delivers a clean digest to Telegram every morning at 8AM. No API key required for arXiv — fully free stack.

---

## 2026-07-01 — GitHub PR Summarizer Bot
**Category:** telegram-bots
**Complexity:** Intermediate
**Description:** Webhook-triggered workflow that catches GitHub PR events (opened, synchronize, reopened), extracts PR metadata via JavaScript, generates an AI summary using Groq LLaMA3, and delivers it instantly to Telegram. Full DevOps + AI integration with ngrok tunneling.

---

## 2026-06-26 — Initial Repo Restructure
**Type:** Repository Organization
**Changes:**
- Reorganized 11 existing workflows into category folders
- Added root `README.md` with badges, workflow table, and quick start
- Added `docs/setup.md` — full Docker + ngrok setup guide
- Added `docs/community-nodes.md` — node reference
- Added `.github/WORKFLOW_TEMPLATE.md` — per-workflow README template
- Added `CHANGELOG.md` (this file)

**Workflows migrated:**
- `AI Email Assistant` → `productivity/ai-email-assistant/`
- `Contract Bot` → `ai-agents/contract-bot/`
- `Image Generator` → `content-automation/image-generator/`
- `Meeting Secretary` → `productivity/meeting-secretary/`
- `PDF ChatBot` → `ai-agents/pdf-chatbot/`
- `Researcher Agent` → `ai-agents/researcher-agent/`
- `Resume Screener` → `productivity/resume-screener/`
- `Social Autopilot` → `content-automation/social-autopilot/`
- `Universal Translator` → `utilities/universal-translator/`
- `Universal Web Reader` → `ai-agents/universal-web-reader/`
- `YouTube Summarizer` → `content-automation/youtube-summarizer/`

---

<!-- New entries go above this line -->