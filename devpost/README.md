# Devpost Submission — AccessKit Studio

Copy the sections below into Devpost, then attach the links.

## Project Title

AccessKit Studio — Accessible Campaigns in Minutes

## Elevator Pitch (1–2 sentences)

AccessKit Studio helps nonprofits, small businesses, and creators turn one campaign brief into an accessible marketing kit — post, captions, poster, alt text, and plain-language version — with a live WCAG accessibility score and a human review gate before export.

## Inspiration

A small nonprofit posted a beautiful event poster — and a blind supporter replied that they had no idea what it said. No alt text, no plain-language version, no captions. The team cared about inclusion; they just didn't have the time, budget, or expertise to check every asset. Accessibility felt like a separate, expert-only job that came after publishing. We built AccessKit so accessibility is in the draft, not bolted on at the end.

## What it does

Type a campaign brief and AccessKit generates a complete kit: social post, caption with CamelCase hashtags, poster preview in your brand colors, real alt text, a plain-language version, and a 30-second captioned video script. It then audits the kit with 7 real checks — WCAG contrast math, reading level, alt text quality, hashtag casing, emoji count, caption planning, plain-language presence — and shows a 0–100 score with a before/after comparison. Export unlocks only after a human confirms 4 review checks.

## How we built it

- **Frontend:** single-file HTML + CSS + vanilla JavaScript (zero install)
- **AI:** built-in generation engine by default; optional Google Gemini 2.0 Flash draft mode via a user-supplied key (stored only in browser local storage)
- **Accessibility engine:** real WCAG 2.1 relative-luminance contrast math, Flesch-Kincaid-style reading-level estimate, platform hashtag/caption rules
- **Cloud / Deployment:** static hosting on Vercel + serverless AI call path; no user data leaves the browser except the optional Gemini request
- **Built With:** HTML, CSS, JavaScript, Gemini API, WCAG 2.1, Vercel

## Challenges we ran into

Making the audit honest. A fake "100/100" badge would be easy, but a score that actually moves when you edit the copy is what makes the tool trustworthy. We made every check recompute live from the edited text — including the CamelCase hashtag rule, which needed an extra pass to handle single-word tags correctly.

## Accomplishments that we're proud of

A working end-to-end product — brief → kit → audit → human review → export — in a single file, with a real accessibility score that drops the moment you weaken the alt text, and a human-review gate that keeps people in charge.

## What we learned

Accessibility is mostly unglamorous details: hashtag casing, contrast ratios, caption planning. The teams that need it most don't need another awareness poster; they need the details handled by default, with a human still in charge.

## What's next

One-click PNG poster export with embedded alt text, more platforms and languages, team workspaces with saved brand kits, and automated .srt caption files for the video script.

## Required Links Checklist

- [ ] GitHub repository (public! test in incognito)
- [ ] Demo video (YouTube, Unlisted — NOT Private)
- [ ] Slides (anyone with the link can view)
- [ ] Live demo URL
- [ ] At least one screenshot in the gallery
