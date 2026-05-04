---
name: natalia-carousel
description: Generates a 5–10 slide content carousel for Telegram, VK, LinkedIn, X, TenChat. Uses natalia-design-system for visual style, natalia-brand-voice for tone. Returns an HTML file with slides + export instructions for PNG/PDF publishing.
version: 1.0.0
---

# natalia · carousel design

Turns one content message into **a 5–10 slide carousel** with the unified visual language of natashabrovkina.com.

## When to use

- Telegram/X post that should be expanded into a carousel from text
- Educational content: "5 copywriting mistakes," "3 Ogilvy principles"
- Campaign / launch announcement
- Case study: before → process → after → result
- Swipe file of insights in the brand voice

## Pre-requisites (read first)

1. **`natalia-brand-voice`** — voice + positioning
2. **`natalia-design-system`** — palette, fonts, components (warm-AI default)

## Inputs

Ask in one message:
1. **Topic / content angle** — what are the slides about?
2. **Slide count** — 5 / 7 / 10? (default 7)
3. **Platform** — Telegram/VK (1080×1080) / LinkedIn/TenChat (1080×1350) / X (1600×900) / Instagram (1080×1080)
4. **Goal** — education / announcement / sale / brand awareness?
5. **CTA on the last slide** — what should the reader do?
6. **Palette** — warm (default) or navy?

If something isn't specified — propose a hypothesis and apply the default.

## Methodology layer

- **OGILVY:** the first slide = headline. Decides whether the carousel opens. Named audience + specific benefit.
- **SCHWARTZ:** identify the platform's awareness level:
  - LinkedIn / TenChat (B2B Product Aware) → case study with numbers
  - Telegram subscribers (already Solution/Product Aware) → mechanism + specifics
  - X (Solution Aware) → contrarian or specific framework
  - Cold VK / Instagram feed (Unaware/Problem Aware) → story or pain
- **HOPKINS:** every slide has at least one number, named entity, or timeframe.

## Slide structure (default 7-slide)

1. **Hook slide** — headline + 1-line subhead
2. **Problem slide** — name the pain precisely
3. **Insight slide** — the framework / principle
4. **Example slide** — concrete case with numbers
5. **Application slide** — how the reader uses this
6. **Common mistake slide** — what NOT to do
7. **CTA slide** — one specific next action

## Output

Generate `carousel.html` — a single HTML file containing all slides, designed to be screenshot or exported via Puppeteer to PNG/PDF for publishing.

Each slide in HTML uses:
- `<div class="slide" data-platform="telegram">` wrapper
- Brand palette tokens from natalia-design-system
- Inter for body, Playfair Italic for accent words
- One key visual element per slide (number, icon, or hairline divider)

Provide export instructions at the end:
```bash
npx puppeteer-cli screenshot carousel.html --selector ".slide" --output slides/
```

## Showcase

- **MEDEA Dent** — "5 dental fears" carousel for Telegram, +30% engagement vs text post.
- **Simbios Marketing** — "How to write an agency proposal" carousel for LinkedIn.

## Invocation

```
/natalia-carousel <topic>
```
