# 🤖 n8n Workflow Library

> A growing collection of production-ready n8n automation workflows — built daily, organized by category, and designed to solve real problems.

![Workflows](https://img.shields.io/badge/workflows-11-blue?style=flat-square)
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

### 🧠 AI Agents
| Workflow | Description | Nodes Used |
|----------|-------------|------------|
| [Researcher Agent](./ai-agents/researcher-agent/) | Multi-step web research agent with source synthesis | HTTP, AI Agent, Google Search |
| [PDF ChatBot](./ai-agents/pdf-chatbot/) | Upload any PDF and chat with it via AI | PDF Extract, Vector Store, AI Chat |
| [Contract Bot](./ai-agents/contract-bot/) | AI reviews contracts and flags risky clauses | PDF, OpenAI, Webhook |
| [Universal Web Reader](./ai-agents/universal-web-reader/) | Reads and summarizes any URL with AI | HTTP Request, Cheerio, OpenAI |

### 🤖 Telegram Bots
| Workflow | Description | Nodes Used |
|----------|-------------|------------|
| *(coming soon)* | | |

### 📋 Productivity
| Workflow | Description | Nodes Used |
|----------|-------------|------------|
| [AI Email Assistant](./productivity/ai-email-assistant/) | Drafts smart email replies using AI | Gmail, OpenAI, Webhook |
| [Meeting Secretary](./productivity/meeting-secretary/) | Transcribes meetings and extracts action items | Audio, Whisper, Notion |
| [Resume Screener](./productivity/resume-screener/) | Scores resumes against a job description | PDF, OpenAI, Google Sheets |

### 📣 Content Automation
| Workflow | Description | Nodes Used |
|----------|-------------|------------|
| [Social Autopilot](./content-automation/social-autopilot/) | Auto-generates and posts social content on schedule | OpenAI, Twitter, LinkedIn |
| [YouTube Summarizer](./content-automation/youtube-summarizer/) | Fetches transcript and summarizes any YouTube video | YouTube, OpenAI, Telegram |
| [Image Generator](./content-automation/image-generator/) | Text prompt → AI image → saved to Drive | OpenAI DALL-E, Google Drive |

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
| **Spotify API** | Music automation and playlist workflows |
| **Community Nodes** | Extended functionality beyond core n8n |

---

## 🚀 Quick Start

### 1. Run n8n with Docker
```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n
```

### 2. Expose with ngrok (for webhooks)
```bash
ngrok http 5678
```
Copy the `https://` URL — use it as your webhook base URL in n8n settings.

### 3. Import a Workflow
1. Open n8n at `http://localhost:5678`
2. Go to **Workflows → Import from File**
3. Select any `workflow.json` from this repo
4. Add your credentials and activate

> **Full setup guide:** [docs/setup.md](./docs/setup.md)

---

## 📦 Community Nodes Used

Some workflows require community nodes. Install them via **Settings → Community Nodes** in n8n:

| Node | Used In |
|------|---------|
| `n8n-nodes-base` | All workflows |
| See [docs/community-nodes.md](./docs/community-nodes.md) | For full list |

---

## 📅 Daily Build Log

This repo is updated daily with one new workflow. Each entry links to the workflow folder.

| Date | Workflow | Category |
|------|----------|----------|
| *Active from Day 1* | Initial 11 workflows migrated and organized | Various |

---

## 🤝 Using These Workflows

All workflows are free to use and adapt. If you build on top of one:
- ⭐ Star the repo
- 🔀 Submit a PR with your improved version
- 🐛 Open an issue if something's broken

---

## 👤 Author

**Saad Zaveri** — AI & Data Science Engineer  
[GitHub](https://github.com/saadzaveri26) · [LinkedIn](https://www.linkedin.com/in/muhammed-saad-zaveri-771875292/)

---

*Built with n8n, curiosity, and one commit at a time.*
