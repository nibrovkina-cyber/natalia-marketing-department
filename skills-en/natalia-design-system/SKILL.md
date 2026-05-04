---
name: natalia-design-system
description: Design system for natashabrovkina.com — tokens, typography, components, layout rules. Used by any agent that generates HTML/CSS (carousel, motion, landing, ad creative).
version: 1.0.0
---

# natalia · design system

**Foundation skill for all visual output.** Any natalia-* agent that generates HTML, images, or layout follows this file.

## Palette — two modes

### `data-palette="warm"` (default, modern AI 2026)
```css
--bg: #F7F4EE;          /* off-white cream background */
--bg-card: #FBF9F4;     /* light card */
--surface: #EFEAE0;     /* deep cream */
--ink: #1F1B16;         /* near-black warm */
--ink-2: #4A4339;
--ink-3: #8A8175;
--accent: #D9542B;      /* rust orange */
--accent-ink: #FFFFFF;
--accent-soft: rgba(217, 84, 43, 0.08);
--halo: rgba(217, 84, 43, 0.18);
--good: #2F6E3F;
--hairline: rgba(31, 27, 22, 0.10);
--hairline-2: rgba(31, 27, 22, 0.06);
```

### `data-palette="navy"` (editorial alternative)
```css
--bg: #F4EFE4;
--bg-card: #FBF7EC;
--surface: #ECE4D2;
--ink: #0E1B33;          /* navy */
--ink-2: #2A3A57;
--ink-3: #6B7891;
--accent: #B8893A;       /* gold leaf */
--accent-ink: #0E1B33;
--hairline: rgba(14, 27, 51, 0.14);
--hairline-2: rgba(14, 27, 51, 0.07);
```

**Rule:** **one accent per screen.** Primary CTA, link hover, inline emphasis. Never in body copy.

## Fonts (Google Fonts)

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:ital,wght@1,400;1,500;1,600&family=JetBrains+Mono:wght@400;500&display=swap">
```

### Type scale

| Element | Family | Size | Weight | Letter-spacing |
|---|---|---|---|---|
| Display (hero) | Inter Display | 96–128px | 600–800 | −0.030em |
| H1 | Inter Display | 64–92px | 600–700 | −0.025em |
| H2 | Inter | 40–52px | 600 | −0.015em |
| H3 | Inter | 24–26px | 600 | −0.005em |
| Body | Inter | 17px / 1.55 | 400 | 0 |
| Eyebrow / kicker | JetBrains Mono | 11px uppercase | 500 | 0.14–0.16em |
| Italic accent (single word) | Playfair Display Italic | matches header | 500 | 0 |
| Price | JetBrains Mono tabular-nums | 56–92px | 500 | 0 |

### Italic accent — usage rule

Use `Playfair Display Italic` ONLY for single accent words inside H1/H2 via class `.italic-display`.

```html
<h1>Ready to <span class="italic-display">double</span> revenue?</h1>
```

Never for an entire headline. Never for body.

## Spacing scale

- **Between sections:** 60–120px desktop (modern AI 2026), not 200px (editorial)
- **Page padding:** 48–64px desktop, 24px mobile
- **Card padding:** 28–48px
- **Border-radius:** 0 default (sharp), up to 14–22px allowed on special cards
- **Hero price / signature numerals:** 56–92px

## Components

### Button (primary CTA)
```css
.btn-primary {
  background: var(--accent);
  color: var(--accent-ink);
  padding: 16px 32px;
  border-radius: 4px;       /* not pill */
  font-weight: 500;
  letter-spacing: -0.01em;
  transition: transform 200ms;
}
.btn-primary:hover { transform: translateY(-2px); }
```

### Button (secondary)
```css
.btn-secondary {
  background: transparent;
  color: var(--ink);
  border: 1px solid var(--hairline);
  padding: 16px 32px;
}
```

### Card
```css
.card {
  background: var(--bg-card);
  padding: 36px;
  border: 1px solid var(--hairline-2);
  border-radius: 0;        /* sharp by default */
  transition: transform 240ms;
}
.card:hover { transform: translateY(-4px); }
```

### Eyebrow / kicker
```css
.kicker {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.16em;
  color: var(--ink-3);
}
```

### Hairline divider
```css
.hairline { border-top: 1px solid var(--hairline); }
```

## Layout patterns

### Hero (modern AI 2026)
- min-height: 80vh (not 100vh — leaves room for sticky nav)
- Display headline + 1-line subhead + 2 CTAs (primary + secondary)
- No 3-stat strip ("47M / 20 / 16") — banned
- One accent on screen (the primary CTA)

### Editorial section
- max-width: 1200–1400px
- Generous vertical padding 80–120px
- Eyebrow → H2 → 2-column body or single column 600px wide

### Pricing tier card
- 3 columns desktop, stacked mobile
- Each card: tier name (kicker) → price (large mono) → 4–6 feature bullets → CTA
- No "Most Popular" badge
- No checkmarks ✓ — use numbers or dots

## Visual prohibitions (hard rules)

- Pill buttons with gradient
- Gradient mesh, purple / pink / blue-violet tones
- Stat-strip "47M / 20 / 16" in hero
- Strikethrough price with arrow →
- "Most Popular" badge
- ✓ checkmarks in feature lists (use numbers/dots)
- Drop-cap (blog-only)
- Playfair for entire headline
- Emojis in headlines (📎 ⚡ 🔥 💎)
- Comparison SaaS table with ✓
- 1:1 card grid for pricing

## Use in other skills

When any natalia-* skill generates HTML or CSS:

1. Import this file first as context
2. Use the palette tokens, never raw hex
3. Use the type scale, never arbitrary sizes
4. Honor the prohibitions above
5. One accent per screen rule

## Reference implementations

- Hero example with all rules applied: `templates/landing/hero-warm.html`
- Pricing tier example: `templates/landing/pricing-warm.html`
- Card example: `templates/landing/card.html`

## Rationale

The palette and type rules come from analysis of editorial sites (Aesop, Kinfolk, Pentagram, Substack Pro, SSENSE) — not SaaS sites (Stripe, Linear, Vercel). The brand competes against agencies on craft, not against SaaS tools on conversion-rate-tested templates. The visual difference is the moat.
