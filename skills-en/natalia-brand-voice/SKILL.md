---
name: natalia-brand-voice
description: Brand voice and tone-of-voice foundation for natashabrovkina.com. Defines HOW every marketing agent writes — palette, typography, voice, what we say / what we never say. Used as context by every other natalia-* skill.
version: 1.0.0
---

# natalia · brand voice

**Foundation skill.** Every natalia-* agent should read this file before generating content so the output matches the brand.

## Positioning

- **Name:** Natalia Brovkina
- **Company:** natashabrovkina.com — AI Marketing Studio
- **Cities:** Moscow, Los Angeles
- **Category:** solo studio with an AI team — not an agency, not a SaaS
- **Telegram:** [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- **GitHub:** [nibrovkina-cyber](https://github.com/nibrovkina-cyber)

## Tone of Voice

**Editorial, confident, no posturing, no marketing jargon.**

We aim at a "Kinfolk magazine," not a "SaaS pricing page." Personal voice of a solo expert, not a corporation.

### What we say (examples)

- "Run it yourself — or hand it to me for 30 days"
- "Doubled revenue for 20 small businesses. Without a team."
- "Set the tone once — the agents remember"
- "No 'let's circle back'"
- "If a job isn't mine, I'll tell you"

### What we DON'T say

- "Unlock your growth potential with AI"
- "Best-in-class marketing automation"
- "Game-changing / Revolutionary / Cutting-edge"
- "A dynamic team of professionals"
- "Quality service, end to end"
- "We make it beautiful" (show, don't tell)
- Any superlative without a number ("best," "reliable")

## Voice across 4 axes

| Axis | Where we are | What it means |
|---|---|---|
| Formal ↔ Conversational | **Conversational** (use casual "you") | "Run it yourself," not "Please run it" |
| Serious ↔ Humorous | **Serious** | Humor only contextual, never as a sales tactic |
| Expert ↔ Friendly | **Expert + personal** | "I run every project myself" |
| Provocative ↔ Cautious | **Provocative** | Name the client's pain directly, no hedging |

## Palette

**ONLY** these colors. No purple / pink / blue-violet / gradient mesh.

### Warm AI (default — for landings and pricing)
| Token | Hex | Use |
|---|---|---|
| `--bg` | `#F7F4EE` | Off-white cream background |
| `--bg-card` | `#FBF9F4` | Light card |
| `--surface` | `#EFEAE0` | Deep cream for sections |
| `--ink` | `#1F1B16` | Near-black warm |
| `--ink-2` | `#4A4339` | Secondary text |
| `--ink-3` | `#8A8175` | Tertiary text / labels |
| `--accent` | `#D9542B` | Rust orange — primary CTA |

### Navy editorial (for longread and case studies)
| Token | Hex | Use |
|---|---|---|
| `--bg` | `#F4EFE4` | Cream |
| `--ink` | `#0E1B33` | Navy |
| `--accent` | `#B8893A` | Gold leaf |

**One accent per screen** — primary CTA, link hover, inline emphasis. **Never** in body copy.

## Typography

Three families, in order of frequency:

### 1. Inter (default) — UI, body, headlines
- Headlines: Inter Display 600, letter-spacing −0.025em to −0.035em
- Body: Inter 400, 17/26 (1.55 line-height)
- Display: 96–128px for hero, h1: 64–92px, h2: 40–52px, h3: 24–26px

### 2. Playfair Display Italic 500 — accent words
- **Single words only** inside h1/h2 as emphasis
- Via CSS class `.italic-display`
- Example: "Ready to *double* revenue?"
- Never for a full headline, never for body

### 3. JetBrains Mono 500 — meta, kickers, prices
- Eyebrow / kicker: 11px, uppercase, letter-spacing 0.14em–0.16em
- Technical metadata ("/ PRICING", "v 1.0 · 04.2026")
- Prices: tabular-nums variant, currency unit smaller

## Spacing

- **Between sections:** 60–120px (modern AI 2026), not 200px (editorial)
- **Page padding:** 48–64px desktop, 24px mobile
- **Card padding:** 28–48px
- **Border-radius:** 0 default (sharp), up to 14–22px allowed on special cards
- **Hero price / signature numerals:** 56–92px

## Visual prohibitions (hard rules)

- Pill buttons with gradient
- ✓ checkmarks in feature lists (use numbers / dots)
- "Most Popular" badge on a pricing tier
- Stat-strip "47M / 20 / 16" in the hero
- Strikethrough price with arrow →
- Drop-cap (that's for blogs, not landings)
- Playfair for an entire headline (only italic words inside)
- Comparison SaaS table with ✓
- Emojis in headlines (📎 ⚡ 🔥 💎)
- Gradient mesh, purple / pink / blue-violet tones
- 1:1 card grid for pricing tiers

## Copywriting tone — formulas

**Hero headline:** `[verb/action] + [number] + [result]. [italic addition].`
- ✅ "Doubled revenue for 20 small businesses. *Without a team.*"
- ✅ "Growing SMB revenue 23–58% in 60 days. *No 'let's circle back.'*"
- ❌ "Quality marketing for businesses"

**CTA:** verb + specific
- ✅ "Download free on GitHub →"
- ✅ "Book · 3 spots →"
- ❌ "Learn more," "Contact us"

**Subhead:** mechanism or time-bound proof
- ✅ "3 free landings. No card. 14-day refund."
- ❌ "Modern solutions for your business"

## Showcase cases (use as examples)

- **MEDEA Dent** — dental clinic, central Moscow, leads ×3.4 in 90 days
- **Simbios Marketing** — agency, conversion-to-lead +58% in 60 days

## Applied in other skills

When any natalia-* skill generates content:

1. Read this file first
2. Check tone against "What we say / What we don't say"
3. Use only the approved palette
4. Inter for headlines, Playfair italic only on a single accent word
5. None of the visual prohibitions above
