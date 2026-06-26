# 🛠️ Local Setup Guide

Everything you need to run these n8n workflows on your own machine.

---

## Prerequisites

| Tool | Version | Install |
|------|---------|---------|
| Docker | Latest | [docs.docker.com](https://docs.docker.com/get-docker/) |
| Node.js | 18+ | [nodejs.org](https://nodejs.org) |
| ngrok | Latest | [ngrok.com/download](https://ngrok.com/download) |

---

## 1. Run n8n with Docker

### Basic (no persistence)
```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  n8nio/n8n
```

### Recommended (with data persistence)
```bash
docker run -d \
  --name n8n \
  --restart unless-stopped \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  -e N8N_BASIC_AUTH_ACTIVE=true \
  -e N8N_BASIC_AUTH_USER=admin \
  -e N8N_BASIC_AUTH_PASSWORD=yourpassword \
  n8nio/n8n
```

n8n will be available at: **http://localhost:5678**

### Useful Docker Commands
```bash
# Stop n8n
docker stop n8n

# Start again
docker start n8n

# View logs
docker logs n8n -f

# Update to latest n8n
docker pull n8nio/n8n
docker stop n8n && docker rm n8n
# Re-run the docker run command above
```

---

## 2. Expose n8n with ngrok (for Webhooks)

Many workflows use **Webhook triggers** — these need a public URL to receive events from Telegram, GitHub, etc.

### Setup ngrok
```bash
# Install ngrok
npm install -g ngrok

# Authenticate (one-time, get token from ngrok.com)
ngrok authtoken YOUR_TOKEN_HERE

# Start tunnel
ngrok http 5678
```

You'll see output like:
```
Forwarding   https://abc123.ngrok.io -> http://localhost:5678
```

### Set the Webhook URL in n8n
1. Go to **Settings → General** in n8n
2. Set **Webhook URL** to your ngrok `https://` URL
3. Save

> ⚠️ **Free ngrok URLs change on restart.** For a permanent URL, use ngrok's paid plan or self-host with a VPS.

---

## 3. Install Community Nodes

Some workflows in this repo use community nodes not included in n8n by default.

1. Open n8n → **Settings → Community Nodes**
2. Click **Install a community node**
3. Enter the npm package name (e.g. `n8n-nodes-puppeteer`)
4. Click **Install** and restart n8n

See [community-nodes.md](./community-nodes.md) for the full list used in this repo.

---

## 4. Import a Workflow

1. Download or clone this repo
2. Open n8n → **Workflows** → **Add Workflow**
3. Click the **⋮ menu → Import from File**
4. Select the `workflow.json` from any workflow folder
5. Add required credentials (each workflow's README lists what's needed)
6. Activate the workflow

---

## 5. Set Up Telegram Bots

Several workflows use Telegram as the user interface.

### Create a Bot
1. Open Telegram, search for **@BotFather**
2. Send `/newbot` and follow the prompts
3. Copy your **Bot Token** (looks like `123456789:ABCdef...`)

### Get Your Chat ID
1. Message your bot once
2. Visit: `https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates`
3. Find the `"id"` inside `"chat"` — that's your Chat ID

### Add to n8n
1. Go to **Credentials → New → Telegram API**
2. Paste your Bot Token
3. Save and use in any Telegram node

---

## 6. Environment Variables (Optional)

For advanced setups, you can use a `.env` file with Docker Compose:

```env
# .env
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=yourpassword
N8N_HOST=0.0.0.0
N8N_PORT=5678
WEBHOOK_URL=https://your-ngrok-url.ngrok.io
```

```yaml
# docker-compose.yml
version: '3.8'
services:
  n8n:
    image: n8nio/n8n
    restart: unless-stopped
    ports:
      - "5678:5678"
    env_file: .env
    volumes:
      - ~/.n8n:/home/node/.n8n
```

```bash
docker-compose up -d
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Webhook not receiving events | Check ngrok is running and URL is set in n8n Settings |
| Community node not found | Restart n8n after installing community nodes |
| Credentials not working | Re-enter them — n8n encrypts on save, check for typos |
| Workflow not triggering | Make sure workflow is **Activated** (green toggle) |
| Docker container exits | Run `docker logs n8n` to see the error |
