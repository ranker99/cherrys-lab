# Cherry's Lab — AI Companion Prompt Generator & Character Builder

**A [Cherry's List](https://www.cherryslist.ai/) tool.** Cherry's Lab is a free, open-source **AI companion prompt generator** — build a character persona in one click, or generate a full, cinematic **system prompt** for your AI girlfriend, AI boyfriend, or roleplay companion. It runs entirely in your browser: no login, no sign-up, no backend, nothing to install.

Paste the output straight into an AI companion / chatbot app that accepts a character definition or system prompt.

Two tools, two tabs:

| Tool | What it does | API key? | Output |
|---|---|---|---|
| **Express** | Instant AI persona generator — dial in five personality traits and get a character sketch in your browser. | No | A short persona paragraph |
| **Studio** | Detailed AI character & system-prompt builder — fill a short brief and an LLM writes a full, in-character system prompt. | Yes — your own (BYOK) | A copy-paste system prompt (length you choose) |

---

## Features

- 🎭 **AI companion persona generator** — a 250-adjective engine across five personality dimensions (Affection, Energy, Dynamic, Depth, Edge)
- 🎬 **Cinematic system-prompt builder** — structured output: Scene, Voice, Contradiction, Triggers, Rules, Examples, and an Opener
- 🎲 **"Surprise me" idea bank** — 40+ options per field to spin up a complete AI character in seconds, plus per-field re-rolls
- 🔑 **Bring your own API key (BYOK)** — works with Anthropic (Claude) and OpenAI (GPT)
- 🔒 **Private by design** — no accounts, no tracking, no analytics; your API key never leaves your browser
- ⚡ **Single HTML file** — clone and open, or host free on GitHub Pages
- 📋 **Copy-paste ready** — drop the prompt into any AI chat, companion, or roleplay app

---

## Works with

Cherry's Lab produces plain, labelled character text, so it works anywhere you can paste a system prompt or character card — **Character.AI, SillyTavern, Janitor AI, Chub / Venus, ChatGPT, Claude, Poe**, and most other AI girlfriend / AI boyfriend / AI companion apps.

---

## Quick start

**Option A — just open it.**
Download `index.html` and double-click it. Express works immediately. (Studio needs a local server or hosting — see the note below.)

**Option B — serve it locally** (recommended, and required for Studio in some browsers):

```bash
# Python 3
python3 -m http.server 8000
```

Then visit **http://localhost:8000** and open Cherry's Lab.

Any static host works too — **GitHub Pages**, Netlify, Vercel, an S3 bucket, whatever. It's one file.

> **Why a server for Studio?** Some browsers restrict outbound API requests from pages opened directly via `file://`. Serving over `http://localhost` (or any host) avoids that. Express is fully static and works either way.

---

## Express — instant AI persona generator

Give your companion a name, then set five discrete sliders — **Affection, Energy, Dynamic, Depth, Edge** — each on a 1–5 scale. Every point on every scale has its own pool of adjectives. Hit **Generate** and Cherry's Lab samples a few descriptors per trait and assembles them into a short persona paragraph, deduplicating so no word repeats. Regenerate as many times as you like for a fresh take at the same settings.

Everything runs in your browser. No key, no network, no waiting — a persona in one click.

---

## Studio — AI system-prompt builder (bring your own API key)

Studio calls a large language model to write a detailed, in-character **system prompt** you can paste into any AI companion app, structured into these sections: **Scene, Voice, Contradiction, Triggers, Rules, Examples, Opener.**

### Adding your API key (BYOK)

1. Switch to the **Studio** tab.
2. Choose your **Provider** — Anthropic (Claude) or OpenAI (GPT).
3. Paste your API key and click **Save**.

- **Anthropic** keys look like `sk-ant-…` — get one at <https://console.anthropic.com/>.
- **OpenAI** keys look like `sk-…` — get one at <https://platform.openai.com/api-keys>.

Your key is stored **only in your browser** (`localStorage`) and is sent **directly to your chosen provider** when you generate. It never passes through a Cherry's List server, because there isn't one. Change or clear the saved key anytime with the **Clear** button.

### Generating a character prompt

Fill in the brief — only **Name**, **Age**, **Role**, **The scene**, and **Word limit** are required; everything else is optional, and the model fills in fitting detail. Stuck for ideas? Hit **🎲 Surprise me** to populate every field from a large built-in idea bank (or re-roll any single field). Click **Generate prompt** — it usually takes 10–30 seconds depending on provider and length. The finished prompt appears in the output panel, where you can **edit it inline** before copying.

---

## Who it's for

Writers, roleplayers, and anyone building an AI companion character who wants a strong, consistent **character prompt** without starting from a blank page. Cherry's Lab does the heavy lifting on persona and voice; you tweak and paste.

---

## Content & safety

Cherry's Lab is a **creative-writing tool for adults**. All generated characters are fictional adults — the generator is instructed to avoid real-person likenesses and to keep output suitable as a character definition.

---

## Privacy

- No accounts, no tracking, no analytics.
- Express sends nothing anywhere — it's fully client-side.
- Studio's only network request goes from your browser directly to your chosen model provider, authenticated with your own API key.

---

## License

[MIT](LICENSE) — do what you like.

---

Made by **[Cherry's List](https://www.cherryslist.ai/)** — independent, hands-on reviews and rankings of the best AI girlfriend, companion, and NSFW AI chat apps. Find your match at **[cherryslist.ai](https://www.cherryslist.ai/)**.
