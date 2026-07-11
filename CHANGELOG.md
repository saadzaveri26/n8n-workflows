# 📅 Changelog

All workflows added to this repo, tracked by date.

---

## 2026-07-11 — Autonomous Research Agent
**Category:** ai-agents
**Complexity:** Advanced
**Description:** First workflow using n8n's AI Agent node instead of Basic LLM Chain — demonstrates true agentic behavior with autonomous tool-calling (Wikipedia lookup), multi-step reasoning, and persistent conversation memory via Simple Memory node. Marks the shift from static LLM chains to dynamic reasoning agents.

## 2026-07-10 — CV JD Match Scorer
**Category:** productivity
**Complexity:** Advanced
**Description:** Telegram bot that accepts a CV PDF with job description as caption, extracts PDF text, scores the match using Groq LLaMA3-70b across skills/experience/education dimensions, logs results to Google Sheets, and delivers detailed analysis with matched/missing skills and verdict.

## 2026-07-09 — AI Code Review Agent
**Category:** ai-agents
**Complexity:** Advanced
**Description:** Webhook-triggered agent that fetches actual git diffs from GitHub API when a PR is opened, sends the diff to Groq LLaMA3-70b for a real code review covering bugs, security and performance, then posts the review as a comment directly on the GitHub PR and sends a summary to Telegram.

---

## 2026-07-07 — LinkedIn Post Generator
**Category:** content-automation
**Complexity:** Beginner-Intermediate
**Description:** Telegram bot that takes any topic and generates a professional LinkedIn post using Groq LLaMA3-70b. Follows LinkedIn best practices — hook opening, structured bullets, engagement question, and relevant hashtags. Optional Google Sheets content calendar logging.

---

## 2026-07-06 — Website Monitor Agent
**Category:** ai-agents
**Complexity:** Intermediate
**Description:** Scheduled daily agent that fetches any website, compares content with previously stored version using n8n static data, and sends AI-powered change analysis to Telegram when differences are detected. No external database needed.

---

## 2026-07-05 — GitHub Activity Digest
**Category:** data-pipelines
**Complexity:** Intermediate
**Description:** Scheduled evening workflow that fetches GitHub profile stats and recent public events via GitHub API, aggregates today's activity, generates a motivational summary using Groq, and delivers it to Telegram daily at 6PM.

---

## 2026-07-04 — AI Job Application Tracker
**Category:** productivity
**Complexity:** Intermediate
**Description:** Telegram bot that uses Groq LLaMA3 to parse natural language job application messages, extract company, role, status and source, then logs everything to Google Sheets automatically.

---

## 2026-07-03 — Smart Expense Logger Bot
**Category:** telegram-bots
**Complexity:** Beginner
**Description:** Telegram bot that parses natural language expense messages like "Coffee 150 food" and automatically logs item, amount, category, date and time to Google Sheets. Uses OAuth2 for Google Sheets authentication.

---

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
- Added root README.md with badges, workflow table, and quick start
- Added docs/setup.md — full Docker + ngrok setup guide
- Added docs/community-nodes.md — node reference
- Added .github/WORKFLOW_TEMPLATE.md — per-workflow README template
- Added CHANGELOG.md (this file)

---

<!-- New entries go above this line -->