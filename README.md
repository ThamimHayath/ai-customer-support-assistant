# NexaSupport AI — Customer Support Assistant

A production-ready AI-powered customer support chatbot built with the **Groq API**. Designed for gaming and SaaS companies, it handles multi-category support conversations with real-time AI responses, escalation detection, and a clean responsive UI.

> 🔗 **[Live Demo](https://ThamimHayath.github.io/ai-customer-support-assistant)**

---

## Preview

![NexaSupport AI Screenshot](screenshot.PNG)

---

## Features

- **5 support categories** — General, Billing, Technical, Account, and Gaming, each with a dedicated AI persona and system prompt
- **Live Groq API integration** — real conversational AI responses, not scripted flows
- **Conversation history** — remembers context within the session for coherent multi-turn dialogue
- **Smart escalation** — detects when an issue needs a human agent and shows a live handoff banner automatically
- **Typing indicator** — animated feedback while the AI processes a response
- **Suggestion chips** — quick-tap prompts for common issues per category
- **Responsive layout** — collapses gracefully on mobile (sidebar icons only)
- **Dark mode** — respects `prefers-color-scheme` automatically
- **Zero dependencies** — single HTML file, no build step, no framework

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| AI | [Anthropic API](https://www.anthropic.com) (` -sonnet-4-6`) |
| Icons | [Tabler Icons](https://tabler-icons.io) (webfont) |
| Hosting | GitHub Pages |

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/ThamimHayath/ai-customer-support-assistant.git
cd ai-customer-support-assistant
```

### 2. Add API key

Open `index.html` and replace the placeholder on line ~170:

```javascript
const API_KEY = 'YOUR_ANTHROPIC_API_KEY';
```

Get a key at [console.anthropic.com](https://console.anthropic.com).

> ⚠️ **Security note:** Embedding an API key directly in the frontend is fine for demos and portfolios. For a production deployment, route API calls through a backend proxy (Node.js, Python, etc.) so the key is never exposed to the browser.

### 3. Open locally

```bash
open index.html
# or just double-click the file
```

No build step, no `npm install` — it works immediately.

---

## Deploy to GitHub Pages

1. Push the repo to GitHub
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch → main → / (root)**
4. Live URL will be: `https://ThamimHayath.github.io/ai-customer-support-assistant`

---

## How It Works

Each support category injects a tailored system prompt into the API call:

```javascript
const systemPrompt = `You are a friendly, professional AI customer support agent for NexaSupport.
You are currently handling ${currentCategory} support queries.
Keep responses concise (2–4 sentences), empathetic, and helpful.
For unresolvable issues, recommend a human agent.`;
```

The full conversation history is sent with every request, giving context for multi-turn support conversations.

---

## Project Structure

```
ai-customer-support-assistant/
├── index.html       # Entire app — HTML, CSS, and JS in one file
├── README.md        # This file
└── screenshot.png   # Demo screenshot 

```

---

## Customisation

| What | Where |
|---|---|
| Brand name | Search `NexaSupport` in `index.html` and replace |
| Categories | Edit the `categories`, `greetings`, and `defaultChips` objects in the `<script>` block |
| AI persona | Modify the `systemPrompt` string inside `sendMessage()` |
| Colour scheme | Update CSS variables in `:root` |
| Model | Change ` -sonnet-4-6` to any supported model |

---

## About the Author

Built by **Thamim M** — Senior Consultant in Gaming & SaaS technical support with 6+ years of ITES experience.

- 🌐 [thamim.online](https://thamim.online)
- 💼 [linkedin.com/in/thamim-m-mtech](https://linkedin.com/in/thamim-m-mtech)
- 🐙 [github.com/ThamimHayath](https://github.com/ThamimHayath)

---

## License

MIT — free to use, modify, and deploy.
