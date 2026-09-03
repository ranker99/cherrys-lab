# Cherry's Lab

**A [Cherry's List](https://www.cherryslist.ai/) tool** — a small, self-contained web app for building AI companion prompts.

Cherry's Lab is a single HTML file with two tools behind two tabs. There's no backend, no database, and nothing to install. Open the file and it works.

| Tool | What it does | Needs an API key? | Output |
|---|---|---|---|
| **Express** | Name her, dial in five personality traits, and generate a persona sketch instantly, in your browser. | No | A short persona paragraph |
| **Studio** | Fill in a short brief and let an LLM write a full, cinematic system prompt for a companion character. | Yes — your own | A ~700–1000 word copy-paste system prompt |

---

## Quick start

**Option A — just open it.**
Download `index.html` and double-click it. Express works immediately. (Studio needs a local server or hosting — see note below.)

**Option B — serve it locally** (recommended, and required for Studio in some browsers):

```bash
# Python 3
python3 -m http.server 8000
```

Then visit **http://localhost:8000** and open Cherry's Lab.

Any static host works too — GitHub Pages, Netlify, Vercel, an S3 bucket, whatever. It's one file.

> **Why a server for Studio?** Some browsers restrict outbound API requests from pages opened directly via `file://`. Serving over `http://localhost` (or any host) avoids that. Express is fully static and works either way.

---

## Express

Give her a name, then set five discrete sliders — **Affection, Energy, Dynamic, Depth, Edge** — each with a 1–5 scale. Every point on every scale has its own pool of adjectives. Hit **Generate** and Cherry's Lab samples a few descriptors per trait and assembles them into a short persona paragraph, deduplicating so no word repeats. Regenerate as many times as you like for a fresh take at the same settings.

Everything runs in your browser. No key, no network, no waiting.

---

## Studio (bring your own API key)

Studio calls a large language model to write a detailed, in-character system prompt with these sections: **Scene, Voice, Contradiction, Triggers, Rules, Examples, Opener.**

### Adding your API key

1. Switch to the **Studio** tab.
2. Choose your **Provider** — Anthropic (Claude) or OpenAI.
3. Paste your API key and click **Save**.

- **Anthropic** keys look like `sk-ant-…` — get one at <https://console.anthropic.com/>.
- **OpenAI** keys look like `sk-…` — get one at <https://platform.openai.com/api-keys>.

Your key is stored **only in your browser** (`localStorage`) and is sent **directly to your chosen provider** when you generate. It never passes through a Cherry's List server, because there isn't one. You can change or clear the saved key at any time with the **Clear** button.

### Generating

Fill in the brief — only **Name**, **Age**, **Role**, **The scene**, and **Word limit** are required; everything else is optional and the model will fill in fitting detail. Stuck for ideas? Hit **🎲 Surprise me** to fill every field from a large built-in idea bank. Click **Generate prompt** when ready. It takes roughly 10–15 seconds. The result appears in the output panel, where you can **edit it inline** before copying.

---

## Notes on content

Cherry's Lab is a creative-writing tool for adults. All generated characters are fictional adults — the generator is instructed to avoid real-person likenesses and to keep output suitable as a character definition.

---

## Privacy

- No accounts, no tracking, no analytics.
- Express sends nothing anywhere.
- Studio's only network request is the one from your browser to your chosen model provider, authenticated with your own key.

---

## License

[MIT](LICENSE) — do what you like.

Made by [Cherry's List](https://www.cherryslist.ai/) · [cherryslist.ai](https://www.cherryslist.ai/)
