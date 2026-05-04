---
name: natalia-campaign-planner
description: Marketing campaign planner. Takes a short brief (product, goal, budget, deadline) and outputs a complete campaign document with positioning, ICP, KPIs, channel mix, budget allocation, content calendar, funnel mapping, accountability. Uses Ogilvy/Schwartz/Hopkins methodology, brand voice, and design system.
version: 1.0.0
---

# natalia · campaign planner

Prepares **a turnkey marketing campaign launch.** Not an audit of existing — **planning from scratch.**

## When to use

- New product / service launch
- Seasonal offer or promotion
- New audience segment
- Relaunch of an old product in new packaging
- You receive a short brief "we need a campaign for X" — you deliver the full plan

## Pre-requisites (read these skills first)

1. **`natalia-brand-voice`** — voice + positioning + what we don't say
2. **`natalia-design-system`** — palette + typography for final artifacts
3. **`natalia-positioning`** — if campaign-specific positioning isn't defined yet
4. **`natalia-competitors`** — if the competitive picture isn't known

## Methodology layer (apply silently)

- **OGILVY:** every hero message and campaign headline is verifiable (number + named-audience + timeframe)
- **SCHWARTZ:** identify the target's awareness level → each channel hits its own level
- **HOPKINS:** measurable KPI for every funnel stage. Without numbers — it's not a plan, it's a diagram

## Inputs from the client

Ask in one message:
1. **Product / service** — what are we launching?
2. **Goal** — revenue / leads / reach / brand awareness?
3. **Deadline** — when does it launch + how many weeks does the campaign run?
4. **Budget** — total and monthly, traffic vs content vs tools
5. **Audience** — who is the target? Awareness level (1–5 Schwartz)?
6. **Geography** — local / national / international?
7. **Current marketing** — what already exists (site, channel, list, ads)?
8. **Competitors** — 2–3 names (optional)

If data is thin — propose hypotheses and mark them as "assumption — confirm before execution."

## Outputs (fixed structure)

Create file `campaigns/<campaign-slug>/CAMPAIGN-BRIEF.md` with:

### 1. Executive summary (1 paragraph)
Product, goal, target, budget, timeline, expected outcome.

### 2. Positioning
- One-line positioning statement
- 3 key messages
- ICP (1 page) with awareness level per segment

### 3. Channel mix + budget allocation
| Channel | Awareness level | Budget | Goal | Owner |
|---|---|---|---|---|
| (each row a channel)

### 4. Funnel map
Traffic → Lead → Qualified → Customer
Conversion rate target at each step + benchmark.

### 5. Content calendar (per week)
| Week | Focus | Deliverables | Channel |
|---|---|---|---|

### 6. KPIs (the only thing measured)
- Primary: 1 number that defines success
- Secondary: 3 supporting numbers
- Anti-metrics: what we deliberately don't optimize

### 7. Accountability
- Who does what
- Weekly review cadence
- Stop-loss criteria (when to abort the campaign)

### 8. Production checklist
Cross-reference which natalia-* skills produce each artifact:
- Landing → `/natalia-landing` or `/natalia-webdesign`
- Email → `/natalia-email`
- Ads → `/natalia-ads`
- Social → `/natalia-social`
- Lead magnet → `/natalia-leadmagnet`
- etc.

## Showcase

- **MEDEA Dent** — 90-day campaign brief produced 12→47 weekly leads.
- **Simbios Marketing** — 60-day relaunch brief produced +58% conversion.

## Invocation

```
/natalia-campaign-planner
```
