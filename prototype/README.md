# Prototype Setup Guide — AccessKit Studio

> Goal: anyone — a judge, a mentor, a teammate — can run this in under 1 minute. No install needed.

## Option A — Open the file (fastest)

1. Download or clone this repo.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Fill in the sample brief (pre-loaded) and click **Generate accessible kit**.

No server, no build step, no dependencies.

## Option B — Serve locally (optional)

```bash
cd accesskit
python3 -m http.server 8000
# open http://localhost:8000
```

## Try it out (30-second test path)

1. Open the app — the sample brief "Free Coding Class for Teens" is pre-filled.
2. Click **Generate accessible kit**.
3. See the kit: post, caption, poster, alt text, plain-language version, video script.
4. Check the **Accessibility audit** — score, 7 checks, before/after.
5. Edit the alt text to a single letter and watch the score drop live.
6. Tick all 4 human-review boxes → **Approve & download kit**.

## Optional: real AI generation (Gemini)

Without a key, AccessKit uses its built-in generation engine. To use Gemini:

1. Get a free key at https://aistudio.google.com
2. Expand "Optional: connect a Gemini API key" in the app, paste it, click Save.
3. Generate again — copy is drafted by Gemini, then audited + human-reviewed the same way.

Your key is stored only in your browser's local storage and sent only to Google's API. Never commit keys to the repo.

## Fallback for judges

- **Live deployment:** *(add Vercel URL after deploy)*
- **Demo video:** *(add YouTube link)*
- **Screenshots:** *(add to this folder)*

## Troubleshooting

- **Blank page** → make sure you opened `index.html` from this repo (not a partial download).
- **Gemini key fails** → the app falls back to the built-in engine automatically and tells you why.
- **Copy buttons don't work** → clipboard access needs a secure context (https or localhost); use Download instead.

## Architecture

```
[ Browser: index.html (single file) ]
   ├── Brief form ──> Generation engine (built-in) ──> Kit (post, caption, poster, alt, plain, script)
   │                    └── optional: Gemini API (user key, localStorage only)
   ├── Audit engine ──> WCAG contrast math + reading level + platform rules ──> Score 0–100
   └── Human review gate (4 checkboxes) ──> Export (.html download)
[ Static hosting: Vercel ] — no backend, no database, no user data stored
```

One sentence per box: the brief feeds the generator; the generator feeds the audit; the audit feeds the human; the human unlocks the export.
