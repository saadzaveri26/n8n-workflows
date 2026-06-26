# 🔧 [Workflow Name]

> One-line description of what this workflow does and why it's useful.

---

## 📌 What It Does

Describe the workflow in 2–4 sentences. What problem does it solve? What does a user experience when running it? What's the output?

---

## 🔁 Flow Diagram

```
[Trigger] → [Step 1] → [Step 2] → [AI / Logic] → [Output]
```

Replace the above with the actual node names, for example:
```
[Telegram Message] → [HTTP Request] → [OpenAI GPT-4] → [Telegram Reply]
```

---

## 🧩 Nodes Used

| Node | Purpose |
|------|---------|
| `Telegram Trigger` | Receives user message |
| `OpenAI` | Generates the response |
| `Telegram` | Sends reply back to user |

> ⚠️ **Community Nodes Required:** List any non-standard nodes here, e.g. `n8n-nodes-puppeteer`

---

## 🔑 Credentials Needed

- [ ] **Telegram Bot Token** — [How to get one](https://core.telegram.org/bots#botfather)
- [ ] **OpenAI API Key** — [platform.openai.com](https://platform.openai.com)
- [ ] *(add others as needed)*

---

## ⚙️ Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Go to **Credentials** and add:
   - Telegram Bot Token
   - OpenAI API Key
3. Update any hardcoded values (chat IDs, spreadsheet URLs, etc.) marked with `⚠️ CONFIGURE`
4. If the workflow uses a **Webhook trigger**, copy the webhook URL and register it with the relevant service
5. **Activate** the workflow using the toggle in n8n

---

## 🌐 Webhook Setup (if applicable)

If this workflow uses a Webhook node:

```bash
# Expose your local n8n with ngrok
ngrok http 5678

# Your webhook URL will look like:
https://abc123.ngrok.io/webhook/your-path
```

Paste this URL in the external service (Telegram, GitHub, etc.)

---

## 📸 Screenshot

*(Add a screenshot of the workflow canvas here)*

![Workflow Screenshot](./screenshot.png)

---

## 💡 Use Cases

- Use case 1
- Use case 2
- Use case 3

---

## 🔮 Possible Extensions

- [ ] Add error handling / fallback branch
- [ ] Log results to Google Sheets
- [ ] Add a confirmation step before taking action
- [ ] Support multiple languages

---

## 📁 Files

| File | Description |
|------|-------------|
| `workflow.json` | Import this into n8n |
| `README.md` | This file |
| `screenshot.png` | Visual of the workflow canvas *(optional)* |

---

*Category: `[ai-agents / telegram-bots / productivity / content-automation / utilities]`*  
*Added: `YYYY-MM-DD`*  
*Complexity: `Beginner / Intermediate / Advanced`*
