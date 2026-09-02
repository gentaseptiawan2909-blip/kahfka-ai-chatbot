# 🤖 Kahfka AI Chatbot

AI-powered customer service chatbot for e-commerce fashion store, built with **n8n** + **Google Gemini 2.5 Flash** + **Telegram Bot API**.

> **Portfolio Project** — Demonstrating no-code/low-code AI automation for real-world business use cases.

---

## 📋 Overview

Kahfka is a dummy customer service chatbot for a fictional online fashion store. Built to showcase how small businesses can automate their CS operations using accessible tools — reducing manual workload while maintaining natural, brand-aligned conversations.

## ✨ Features

- 💬 **Multi-turn conversation** with context memory per user
- 🎯 **Custom business persona** via system prompt engineering
- 🛡️ **Guardrails** against out-of-scope questions (e.g. rejects "iPhone?" queries)
- 🚫 **Anti-hallucination** — never invents prices, stock, or promo info
- 👥 **Session isolation** — each user gets separate memory context
- 🔄 **Graceful handoff** — suggests contacting human admin for complex issues

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Automation Platform | n8n (self-hosted) |
| LLM | Google Gemini 2.5 Flash |
| Messaging Interface | Telegram Bot API |
| Memory Store | n8n Simple Memory (session-based) |
| Tunneling (dev) | ngrok |

## 🏗️ Workflow Architecture
Telegram Trigger → AI Agent (Gemini) → Send Message
↓
Simple Memory

Nodes used:
- **Telegram Trigger** — listens for incoming messages
- **AI Agent** — orchestrates LLM + memory + tools
- **Google Gemini Chat Model** — handles inference
- **Simple Memory** — stores conversation history per chat ID
- **Telegram Send Message** — replies to user

## 💼 Business Use Cases

- E-commerce customer service automation
- Product inquiry & FAQ handling
- Order status & shipping information
- Return/refund policy assistance
- Estimated to reduce human CS workload by 60-80%

## 📸 Demo

[Video demo coming soon]

Example conversations:
- Product inquiry: *"Halo, jual apa aja?"*
- Out-of-scope handling: *"Ada iPhone 15?"*  → politely redirected
- Multi-turn memory: *"Saya mau beli jaket"* → *"Ada ukuran XL?"*

## 🚀 Setup (for replication)

**Prerequisites:**
- Node.js 18+
- n8n installed (`npm install -g n8n`)
- Telegram Bot Token (from @BotFather)
- Google Gemini API Key (from Google AI Studio)

**Steps:**
1. Start n8n: `n8n start`
2. Start ngrok tunnel: `ngrok http 5678`
3. Import workflow JSON (see `/workflow` folder)
4. Configure credentials for Telegram & Gemini
5. Activate workflow
6. Test via Telegram

## 📁 Project Structure
kahfka-ai-chatbot/
├── README.md
├── workflow/
│ └── kahfka-workflow.json # n8n workflow export
├── screenshots/
│ ├── canvas.png
│ └── telegram-demo.png
└── docs/
└── system-prompt.md # AI persona configuration

## 🔮 Future Roadmap

- [ ] Deploy to VPS for 24/7 uptime
- [ ] Integrate with real product database (Google Sheets / Airtable)
- [ ] Add error handling & retry logic
- [ ] Support WhatsApp Business API
- [ ] Add analytics dashboard for common queries
- [ ] Implement session timeout (24h idle reset)

## 👤 Author

**Redpanda** — Civil Engineer transitioning into AI Automation
- 🔗 [LinkedIn]([https://linkedin.com/in/your-profile](https://www.linkedin.com/in/gentaseptiawan/))
- 📧 Available for freelance AI automation projects

## 📄 License

MIT License — feel free to use as reference for your own projects.

---

*Built as part of AI Automation Engineer portfolio, 2026*
