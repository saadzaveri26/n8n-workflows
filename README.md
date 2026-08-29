# 🤖 n8n Workflow Library

> A growing collection of production-ready n8n automation workflows — built daily, organized by category, and designed to solve real problems.

![Workflows](https://img.shields.io/badge/workflows-19-blue?style=flat-square)
![Stack](https://img.shields.io/badge/stack-n8n%20%7C%20Docker%20%7C%20Telegram-orange?style=flat-square)
![Maintained](https://img.shields.io/badge/maintained-actively-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)

---

## 📁 Repository Structure

```
n8n-workflows/
├── ai-agents/              # Autonomous agents that research, reason, and act
├── telegram-bots/          # Telegram-powered interfaces and notification systems
├── productivity/           # Email, meetings, documents, and task automation
├── content-automation/     # Social media, YouTube, image, and content pipelines
├── data-pipelines/         # Scraping, transformation, and storage workflows
├── utilities/              # Reusable helper workflows and building blocks
└── docs/                   # Setup guides and node references
```

---

## ⚡ Workflows

### 🤖 Telegram Bots
| Workflow | Description | Nodes Used | Added |
|----------|-------------|------------|-------|
| [GitHub PR Summarizer](./telegram-bots/github-pr-summarizer/) | Webhook-triggered bot that catches GitHub PRs and sends AI summaries to Telegram instantly | Webhook, Code, IF, Groq, Telegram | 2026-07-01 |
| [arXiv ML Daily Digest](./telegram-bots/arxiv-ml-digest/) | Fetches 5 latest ML/AI papers from arXiv every morning and delivers AI-summarized digest to Telegram | Schedule, HTTP Request, Code, Groq, Telegram | 2026-07-02 |
| [Smart Expense Logger](./telegram-bots/smart-expense-logger/) | Send expense messages to Telegram bot and auto-log to Google Sheets with date and category | Telegram Trigger, Code, Google Sheets, Telegram | 2026-07-03 |

### 🧠 AI Agents
| Workflow | Description | Nodes Used | Added |
|----------|-------------|------------|-------|
| [Website Monitor Agent](./ai-agents/website-monitor-agent/) | Daily scheduled agent that detects website changes and sends AI-powered analysis to Telegram | Schedule, HTTP Request, Code, IF, Groq, Telegram | 2026-07-06 |
| [AI Code Review Agent](./ai-agents/ai-code-reviewer/) | Fetches git diffs when PRs are opened and posts AI code reviews directly as GitHub PR comments | Webhook, HTTP Request, Code, Groq, Telegram | 2026-07-09 |
| [Researcher Agent](./ai-agents/researcher-agent/) | Multi-step web research agent with source synthesis | HTTP, AI Agent, Google Search | — |
| [PDF ChatBot](./ai-agents/pdf-chatbot/) | Upload any PDF and chat with it via AI | PDF Extract, Vector Store, AI Chat | — |
| [Contract Bot](./ai-agents/contract-bot/) | AI reviews contracts and flags risky clauses | PDF, OpenAI, Webhook | — |
| [Universal Web Reader](./ai-agents/universal-web-reader/) | Reads and summarizes any URL with AI | HTTP Request, Cheerio, OpenAI | — |
| [Autonomous Research Agent](./ai-agents/autonomous-research-agent/) | Tool-calling AI agent using n8n AI Agent node with Wikipedia lookup and conversation memory — demonstrates real agentic reasoning vs simple LLM chains | Telegram Trigger, AI Agent, Groq, Wikipedia Tool, Simple Memory, Telegram | 2026-07-11 |
| [RAG Document Q&A](./ai-agents/rag-document-qa/) | Two-workflow RAG system — ingests documents into a vector store and answers questions grounded in the document content using semantic search + Groq | Telegram Trigger, Text Splitter, Embeddings, Vector Store, Groq, Telegram | 2026-07-12 |

### 📋 Productivity
| Workflow | Description | Nodes Used | Added |
|----------|-------------|------------|-------|
| [AI Job Application Tracker](./productivity/job-application-tracker/) | Telegram bot that uses Groq AI to extract and log job application details to Google Sheets | Telegram Trigger, Groq, Code, Google Sheets, Telegram | 2026-07-04 |
| [AI Email Assistant](./productivity/ai-email-assistant/) | Drafts smart email replies using AI | Gmail, OpenAI, Webhook | — |
| [Meeting Secretary](./productivity/meeting-secretary/) | Transcribes meetings and extracts action items | Audio, Whisper, Notion | — |
| [Resume Screener](./productivity/resume-screener/) | Scores resumes against a job description | PDF, OpenAI, Google Sheets | — |
| [CV JD Match Scorer](./productivity/cv-jd-match-scorer/) | Send CV PDF + job description to Telegram bot and get AI-powered match score with skills gap analysis | Telegram Trigger, Code, IF, HTTP Request, Extract from File, Groq, Google Sheets, Telegram | 2026-07-10 |
| [Voice Note Task Extractor](./productivity/voice-note-task-extractor/) | Transcribes Telegram voice notes using Groq Whisper and extracts structured action items with due dates and priority, logged to Google Sheets | Telegram Trigger, HTTP Request, Groq Whisper, Basic LLM Chain, Code, Google Sheets, Telegram | 2026-07-13 |

### 📣 Content Automation
| Workflow | Description | Nodes Used | Added |
|----------|-------------|------------|-------|
| [LinkedIn Post Generator](./content-automation/linkedin-post-generator/) | Takes any topic and generates a professional LinkedIn post using Groq LLaMA3-70b | Telegram Trigger, Groq, Telegram | 2026-07-07 |
| [Social Autopilot](./content-automation/social-autopilot/) | Auto-generates and posts social content on schedule | OpenAI, Twitter, LinkedIn | — |
| [YouTube Summarizer](./content-automation/youtube-summarizer/) | Fetches transcript and summarizes any YouTube video | YouTube, OpenAI, Telegram | — |
| [Image Generator](./content-automation/image-generator/) | Text prompt → AI image → saved to Drive | OpenAI DALL-E, Google Drive | — |

### 🔄 Data Pipelines
| Workflow | Description | Nodes Used | Added |
|----------|-------------|------------|-------|
| [GitHub Activity Digest](./data-pipelines/github-activity-digest/) | Daily scheduled digest of your GitHub profile stats and activity sent to Telegram | Schedule, HTTP Request x2, Code, Groq, Telegram | 2026-07-05 |

### 🔧 Utilities
| Workflow | Description | Nodes Used |
|----------|-------------|------------|
| [Universal Translator](./utilities/universal-translator/) | Detects language and translates any text | OpenAI, Webhook, Telegram |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **n8n** (Docker) | Workflow automation engine |
| **ngrok** | Expose local n8n to the internet for webhooks |
| **Telegram Bot API** | Primary interface for most user-facing bots |
| **Groq** | Fast LLM inference (LLaMA3) for AI summarization |
| **Google Sheets** | Data logging and storage |
| **GitHub API** | PR events, diffs, and comment posting |
| **arXiv API** | Free ML/AI paper feed |

---

## 🚀 Quick Start

### 1. Run n8n with Docker
```bash
docker run -d \
  --name n8n \
  -p 5679:5678 \
  -e WEBHOOK_URL=https://your-ngrok-domain.ngrok-free.dev \
  -v n8n_data:/home/node/.n8n \
  n8nio/n8n
```

### 2. Start ngrok tunnel (in a separate terminal)
```bash
ngrok http 5679 --url=your-static-domain.ngrok-free.dev
```

### 3. Import a Workflow
1. Open n8n at `http://localhost:5679`
2. Go to **Workflows → Create Workflow**
3. Click **⋯ → Import from File**
4. Select any `workflow.json` from this repo
5. Add credentials and publish

> **Full setup guide:** [docs/setup.md](./docs/setup.md)

---

## 📅 Daily Build Log

| Date | Workflow | Category | Status |
|------|----------|----------|--------|
| 2026-07-09 | [AI Code Review Agent](./ai-agents/ai-code-reviewer/) | ai-agents | ✅ Live |
| 2026-07-07 | [LinkedIn Post Generator](./content-automation/linkedin-post-generator/) | content-automation | ✅ Live |
| 2026-07-06 | [Website Monitor Agent](./ai-agents/website-monitor-agent/) | ai-agents | ✅ Live |
| 2026-07-05 | [GitHub Activity Digest](./data-pipelines/github-activity-digest/) | data-pipelines | ✅ Live |
| 2026-07-04 | [AI Job Application Tracker](./productivity/job-application-tracker/) | productivity | ✅ Live |
| 2026-07-03 | [Smart Expense Logger](./telegram-bots/smart-expense-logger/) | telegram-bots | ✅ Live |
| 2026-07-02 | [arXiv ML Daily Digest](./telegram-bots/arxiv-ml-digest/) | telegram-bots | ✅ Live |
| 2026-07-01 | [GitHub PR Summarizer](./telegram-bots/github-pr-summarizer/) | telegram-bots | ✅ Live |
| 2026-06-26 | Initial 11 workflows migrated and repo restructured | various | ✅ Done |

---

## 🤝 Using These Workflows

All workflows are free to use and adapt.
- ⭐ Star the repo
- 🔀 Submit a PR with your improved version
- 🐛 Open an issue if something's broken

---

## 👤 Author

**Saad Zaveri** — AI & Data Science Engineer
[GitHub](https://github.com/saadzaveri26) · [LinkedIn](https://www.linkedin.com/in/muhammed-saad-zaveri-771875292/)

---

*Built with n8n, curiosity, and one commit at a time.*