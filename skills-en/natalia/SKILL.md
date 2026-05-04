---
name: natalia
description: Marketing department of 21 AI agents plus a campaign-manager orchestrator. Methodology by Ogilvy, Schwartz, and Hopkins. Built originally for Russian SMB but channel-neutral. Part of natashabrovkina.com by Natalia Brovkina. Open source, MIT.
version: 1.1.0
---

# natalia · marketing department · campaign manager

**21 AI agents** plus an orchestrator for small-business marketing. Direct response methodology of **Ogilvy / Schwartz / Hopkins** baked into every agent.

Operates as a **campaign manager**: give it a short brief, the orchestrator dispatches the right skills, and the result is a complete deliverable.

## Architecture

### Foundation skills (always loaded first)

| Skill | What it sets |
|---|---|
| `natalia-brand-voice` | Voice, positioning, tone, what we say and what we never say |
| `natalia-design-system` | Palette, typography, components for every visual artifact |

### Function skills (everyday tasks)

| Command | Agent | When to call |
|---|---|---|
| `/natalia-positioning` | Positioning | Start of any campaign, every new product |
| `/natalia-copy` | Direct response | Landing pages, ads, email — main copywriting |
| `/natalia-leadmagnet` | Lead magnet | Free-tier content for top-of-funnel |
| `/natalia-landing` | Landing / CRO | Audit and rewrite of landing pages |
| `/natalia-email` | Email sequences | Welcome, nurture, launch |
| `/natalia-atomizer` | Atomizer | One post → 15 formats |
| `/natalia-social` | Telegram / VK / X | 30-day content plan |
| `/natalia-ads` | Paid ads | VK Ads, Yandex.Direct, Meta — creative variants |
| `/natalia-seo` | SEO / GEO | Search rankings plus AI-search visibility |
| `/natalia-competitors` | Competitors | Recon and differentiation |
| `/natalia-funnel` | Sales funnel | Customer journey maps, drop-off points |
| `/natalia-launch` | Product launch | Pre-launch → launch → growth playbook |
| `/natalia-brand` | Brand voice | Tone of voice, personal brand |
| `/natalia-newsletter` | Newsletter | Content newsletter that gets opened |
| `/natalia-webdesign` | Site design | Full HTML landing page from a description |
| `/natalia-proposal` | Client proposal | B2B proposals that close |

### Specialty skills (visual artifacts)

| Command | Agent | When to call |
|---|---|---|
| `/natalia-campaign-planner` | Campaign brief | Launch a new campaign from zero to plan |
| `/natalia-carousel` | Carousel design | 5–10 slide visual post |
| `/natalia-motion` | Animated motion | 30–60 second HTML video |

## How the campaign manager works

When the user writes something like:

> "Launching a new B2B sales course, $2.5K budget, 60 days to launch."

The orchestrator does this:

### Step 1 — Foundation
Loads `natalia-brand-voice` and `natalia-design-system` as context.

### Step 2 — Strategic planning
Calls `natalia-campaign-planner`, which:
- Asks 8 clarifying inputs (product, ICP, KPI, etc.)
- Runs research (via WebSearch if available)
- Produces `CAMPAIGN-BRIEF.md` with positioning, channel mix, funnel, budget

### Step 3 — Sharper positioning if needed
If the brief's positioning is thin or competitor context is missing:
- `natalia-competitors` for recon
- `natalia-positioning` for the angle

### Step 4 — Production assets
In parallel (or sequenced by priority):
- `natalia-landing` or `natalia-webdesign` — the campaign landing
- `natalia-copy` — hero + CTA + body
- `natalia-email` — welcome + nurture + launch sequences
- `natalia-ads` — creatives per channel
- `natalia-social` — content plan for Telegram, VK, or X
- `natalia-leadmagnet` — opt-in offer for top of funnel

### Step 5 — Visual layer
- `natalia-carousel` — educational social posts
- `natalia-motion` — hero video for the landing
- `natalia-newsletter` — weekly update issue

### Step 6 — Output

Generates a `campaigns/<slug>/` folder containing:
- `CAMPAIGN-BRIEF.md` — strategy document
- `landing.html` — finished landing page
- `emails/` — sequence
- `ads/` — creatives per channel
- `social-calendar.md` — 30–60 day content plan
- `carousels/` — visual posts
- `motion.html` — explainer video
- `tracker.md` — KPIs, what to measure, where to look

## User workflows

### Minimal path
```
/natalia-campaign-planner
```
Gives you the strategy and plan only. You decide which production skills to call next.

### Full path — orchestration
```
Run a full campaign: B2B sales course, $2.5K budget, 60 days.
```
The orchestrator asks clarifying questions and calls every needed skill in sequence.

### Ad hoc — pinpoint task
```
/natalia-landing https://my-site.com
/natalia-carousel  topic: "5 copywriting mistakes"
/natalia-ads  for B2B sales course
```
Every skill stands alone when you don't need a full campaign.

## Methodology (apply implicitly across all skills)

- **OGILVY** — headlines and positioning. Every product claim must be verifiable (number + named audience + timeframe). No "high-quality / best / professional".
- **SCHWARTZ** — identify the awareness level (1–5) before writing. One piece of content does not work across all five levels.
- **HOPKINS** — advertising is salesmanship in print. Concrete numbers, facts, cases. "92% returned out of 847" beats "most are happy."

## Localization context

The skills were built originally for the Russian SMB market and reference RU-specific channels (Yandex.Direct, VK Ads, Telegram Ads, TenChat, YooKassa, Wildberries, Yandex.Metrica). They translate cleanly to other markets — substitute the local equivalents (Google Ads / Meta Ads / Stripe / Amazon / GA4) and the methodology applies unchanged.

The Russian advertising-mark requirement (ORD, ERID token) is a local legal step — skip it outside Russia.

## Showcase

Walked-through in the YouTube demo:
- **MEDEA Dent** — dental clinic, central Moscow, leads ×3.4 in 90 days
- **Simbios Marketing** — agency, conversion-to-lead +58% in 60 days

## Skill versioning

Every sub-skill has `version: x.y.z` in its frontmatter. On update — bump minor (x.Y.z) for backwards-compatible changes, major (X.y.z) for breaking ones.

When you `cp -r` skills into your local Claude folder, check the version in `SKILL.md` — it should be at least as fresh as your previous copy.

## Author & License

**Natalia Brovkina**
- Site: [natashabrovkina.com](https://natashabrovkina.com)
- Telegram: [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- GitHub: [nibrovkina-cyber/natalia-marketing-department](https://github.com/nibrovkina-cyber/natalia-marketing-department)

MIT — fork, adapt, ship changes back.
