---
name: natalia-motion
description: Generates a 30–60 second HTML video (CSS keyframes + SVG animation) for landing pages, hero sections, or social media. Uses natalia-design-system. Returns a single HTML file ready to embed or export to MP4.
version: 1.0.0
---

# natalia · animated motion

Creates a **30–60 second HTML animation** in brand style for:
- Landing hero as explainer
- YouTube as story visual
- Ad creative for Meta/VK Ads (export → MP4)
- Telegram channel (loop GIF)
- LinkedIn video post

## When to use

- Explainer for a new product without filming
- Animation for pitch presentations
- "Native video" lead magnet for newsletters
- Hero loop on a landing page to convey product feel

## Pre-requisites

1. **`natalia-brand-voice`** — voice + positioning
2. **`natalia-design-system`** — palette, fonts, motion rules

## Inputs

Ask in one message:
1. **Topic / story** — what are we showing? (product launch / explainer / testimonial / showcase)
2. **Duration** — 15s / 30s / 60s? (default 30s)
3. **Where it runs** — landing hero / YouTube / VK Ads / Telegram?
4. **Format** — landscape (16:9 1920×1080) / square (1:1 1080×1080) / vertical (9:16 1080×1920)?
5. **Core message** — one or two phrases that should stick in memory
6. **End CTA** — where does the viewer go?

## Methodology layer

- **OGILVY:** the first 3 seconds = hook. Visual + headline in the first frame. Without a hook, no one watches further.
- **SCHWARTZ:** for social-feed audiences (level 1–2) — open with pain or provocation. For landing-site visitors (level 3–4) — show mechanism or benefit immediately.
- **HOPKINS:** every claim is verifiable. "847 clients in 90 days" stays on screen, "we are professionals" never appears.

## Standard motion techniques

| Technique | When | CSS |
|---|---|---|
| Type fade-in | Headline appears | `opacity 0 → 1, translateY(20px → 0), 800ms ease-out` |
| Counter | Number counts up | `@keyframes count + JS for incremental update` |
| Dot pulse | 21 agents | `scale 1 → 1.15 → 1, opacity 0.3 → 0.85, 2.6s infinite` |
| Underline draw | Underline a word | `width: 0 → 100%, 600ms ease` |
| Scale-reveal | Logo / brand mark | `transform scale(0.9 → 1), opacity 0 → 1, 1s` |
| Marquee | Scrolling testimonials | `translateX 0 → -100%, 20s linear infinite` |
| Slide stack | Before/after sequence | `transform translateX, 600ms ease` |

**Banned:** WebGL, three.js, Lottie. Simple HTML/CSS/SVG only — exports cleanly to MP4 via Puppeteer + ffmpeg.

## 30-second hero-explainer storyboard (default)

```
00:00–00:03  Hook: "Doubled revenue for 20 small businesses" (Inter Display 96px, fade-in)
00:03–00:08  Problem: "Tired of writing copy?" (Playfair italic accent on "writing")
00:08–00:14  Solution: 21 dot-agents appear sequentially (gold dots, pulse)
00:14–00:22  Process: 3 steps — brief → AI works → finished landing (split screens)
00:22–00:28  Proof: "MEDEA Dent: ×3.4 leads in 90 days" (number counter animation)
00:28–00:30  CTA: "natashabrovkina.com/tool — try free" (call-to-action button slide-in)
```

Each frame includes:
- Start time and end time
- Main visual (typography / shape / icon)
- Animation (fade / slide / scale / counter)
- Audio cue (if voice-over) — optional

## Output

Single HTML file with embedded SVG and CSS keyframes. Designed for:
- Direct embed in landing page via `<iframe>` or copy-paste
- Export to MP4 via Puppeteer screen recording + ffmpeg
- Export to GIF via ffmpeg conversion

Provide export instructions:
```bash
# MP4 export
npx puppeteer-recorder motion.html --duration 30 --output motion.mp4

# GIF export from MP4
ffmpeg -i motion.mp4 -vf "fps=15,scale=720:-1:flags=lanczos" motion.gif
```

## Showcase

- **MEDEA Dent** — 30s landing hero loop showing patient anxiety relief flow.
- **Simbios Marketing** — 60s explainer for B2B sales course launch.

## Invocation

```
/natalia-motion <topic / story>
```
