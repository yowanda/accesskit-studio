# AccessKit Studio

**AccessKit Studio helps nonprofits, small businesses, and creators turn one campaign brief into an accessible marketing kit — in under a minute.**

## Inspiration

It started when a small nonprofit posted a beautiful event poster — and a blind supporter replied that they had no idea what it said. No alt text. No plain-language version. No captions. The team cared about inclusion; they just didn't have the time, budget, or expertise to check every asset.

We asked around: every small team we talked to had shipped inaccessible content — not from indifference, but because accessibility felt like a separate, expert-only job that came *after* publishing. Accessibility shouldn't be a filter applied at the end. It should be built into the draft.

## What it does

Type a campaign brief (name, audience, message, tone, call to action) and AccessKit generates:

- **Social post** — platform-ready copy in your tone
- **Caption + CamelCase hashtags** — screen-reader friendly by construction
- **Poster preview** — with your brand colors, checked live for WCAG contrast
- **Alt text** — a real description of the poster, not "image"
- **Plain-language version** — short sentences, no jargon, reading level shown
- **30-second video script** — with captions planned in

Then it **audits** the kit with 7 real checks (WCAG contrast math, reading level, alt text quality, hashtag casing, emoji count, caption planning, plain-language presence) and shows a **0–100 accessibility score** with a before/after comparison.

Finally, **human review**: export unlocks only after you confirm 4 checks. AI drafts, humans decide.

## How we built it

- **Frontend:** single-file HTML + CSS + vanilla JavaScript — zero install, runs anywhere
- **AI:** built-in generation engine by default; optional Google Gemini (2.0 Flash) draft mode via a user-supplied API key stored only in the browser's local storage
- **Accessibility engine:** real WCAG 2.1 relative-luminance contrast math, Flesch-Kincaid-style reading-level estimate, platform hashtag/caption rules
- **Cloud:** static hosting (Vercel) + serverless AI call path; no user data leaves the browser except the optional Gemini request
- **Built With:** HTML, CSS, JavaScript, Gemini API, WCAG 2.1, Vercel

## Challenges we ran into

The hardest part was honesty in the audit: a fake "100/100" badge would be easy, but a score that actually moves when you edit the copy is what makes the tool trustworthy. We made every check recompute live from the edited text — including the CamelCase hashtag rule, which took an extra pass to get right for single-word tags.

## Accomplishments that we're proud of

- A working end-to-end product: brief → kit → audit → human review → export, in one file
- A real accessibility score (not a badge) that drops the moment you weaken the alt text
- Human-review gate: export is locked until a person confirms the checks

## What we learned

Accessibility is mostly unglamorous details — hashtag casing, contrast ratios, caption planning. The teams that need it most don't need another awareness poster; they need the details handled by default, with a human still in charge.

## What's next

- One-click image export of the poster (PNG) with embedded alt text
- More platforms (TikTok, WhatsApp Status) and more languages
- Team workspaces + saved brand kits in the cloud
- Automated caption file (.srt) generation for the video script

## Try it

Open `index.html` in any browser — no install, no keys needed. Or read the setup guide in `prototype/`.

## Submission links

- Repo: https://github.com/yowanda/accesskit-studio
- Live demo: https://yowanda.github.io/accesskit-studio/
- Demo video (2 min): *(add after recording)*
- Slides: *(add link)*
- Devpost write-up: see `devpost/`
