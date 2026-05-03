# natalia-marketing-department · 21 AI agents replacing a marketing department

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../LICENSE)
[![Claude Skills](https://img.shields.io/badge/Claude-Skills-orange)](https://docs.claude.com/en/docs/claude-code/skills)

**21 open-source Claude Skills replacing a marketing department for small business.** Direct response methodology by Ogilvy / Schwartz / Hopkins baked into every agent. MIT licensed. Runs on Claude Code with Anthropic API ($5–30/month).

🇷🇺 [Russian README](../README.md)

## Why this exists

A full-time marketer in Russia costs 100–200K RUB/month (~$1,100–$2,200). Marketing agencies start at 150K RUB. Most small businesses can't afford either — but still need positioning, copywriting, landing pages, email sequences, ads, SEO, competitor research.

This repo packages 21 narrow AI agents (one task each) that do that work. Real cases: a dental clinic in Moscow grew from 12 to 47 weekly leads in 6 weeks. A Greek café cut content production from 20 hours/week to 4.

## What's inside

21 task-specific agents on **Ogilvy / Schwartz / Hopkins** methodology:

| # | Command | Job |
|---|---|---|
| 01 | `/natalia-positioning` | Find the angle that makes you different |
| 02 | `/natalia-copy` | Direct response copy by Schwartz, Hopkins, Ogilvy |
| 03 | `/natalia-leadmagnet` | Lead magnet: offer + full build |
| 04 | `/natalia-landing` | Landing page audit + rewrite |
| 05 | `/natalia-email` | Welcome / nurture / launch sequences |
| 06 | `/natalia-atomizer` | 1 post → 15 formats for all platforms |
| 07 | `/natalia-social` | Telegram / VK content plan + Russian ad markup |
| 08 | `/natalia-ads` | VK Ads + Yandex Direct — copy, audiences, CPL |
| 09 | `/natalia-seo` | Yandex / Google / GEO for AI search |
| 10 | `/natalia-competitors` | 7-point competitor recon |
| 11 | `/natalia-funnel` | CJM, drop-off points, conversion lift |
| 12 | `/natalia-launch` | Launch playbook: pre-launch → launch → growth |
| 13 | `/natalia-brand` | Tone of voice for LinkedIn / TenChat |
| 14 | `/natalia-newsletter` | Content newsletter people wait for |
| 15 | `/natalia-webdesign` | Describe business → get HTML landing |
| 16 | `/natalia-proposal` | Proposals that get read and signed |
| 17 | `/natalia-brand-voice` | Voice/tone foundation for all agents |
| 18 | `/natalia-design-system` | Design tokens + components for HTML/CSS outputs |
| 19 | `/natalia-campaign-planner` | Full campaign from brief: positioning → KPI → calendar |
| 20 | `/natalia-carousel` | 5–10 slide carousel for Telegram / VK / TenChat |
| 21 | `/natalia-motion` | HTML video (CSS keyframes + SVG) for landing/social |

Plus master `natalia` orchestrator that knows about all 21.

## Install (5 minutes)

### Requirements
- [Claude Code](https://claude.com/claude-code) (free)
- Anthropic API key — [console.anthropic.com](https://console.anthropic.com)

### Step 1 — clone repo

```bash
git clone https://github.com/nibrovkina-cyber/natalia-marketing-department.git
cd natalia-marketing-department
```

### Step 2 — install skills

**macOS / Linux:**
```bash
mkdir -p ~/.claude/skills
cp -r skills/* ~/.claude/skills/
```

**Windows (PowerShell):**
```powershell
$src = ".\skills\"
$dst = "$env:USERPROFILE\.claude\skills\"
New-Item -ItemType Directory -Force -Path $dst
Copy-Item -Path $src* -Destination $dst -Recurse -Force
```

### Step 3 — run in Claude Code

Open any project folder. Type:

```
/natalia-positioning
```

Or:

```
Use natalia-landing skill on https://yoursite.com
```

## Methodology

Three principles, each baked into every agent:

### Ogilvy — *headlines = 80%*
Every product claim must be **verifiable**. Adjectives like "high-quality", "best", "professional" — banned. Replace with a number, comparison, or quote.

### Schwartz — *5 awareness levels*
Before any output, the agent mentally identifies the audience level:
1. **Unaware** — don't know they have a problem
2. **Problem Aware** — know the pain, don't know solutions
3. **Solution Aware** — know solutions exist
4. **Product Aware** — know about you, haven't bought
5. **Most Aware** — ready to buy

Email at the wrong level = unsubscribe. Landing at the wrong level = empty cart.

### Hopkins — *Scientific Advertising*
Advertising = a salesperson in print. A salesperson doesn't say "we're a team of professionals", they say "847 clients, 92% returned".

## Russian market adaptations

- **Traffic channels:** Yandex.Direct, VK Ads, Telegram Ads, TenChat
- **Payment:** YooKassa, SBP, Tinkoff Business, Robokassa
- **Analytics:** Yandex.Metrica, Roistat, Calltouch
- **Marketplaces:** Wildberries, Ozon, Yandex.Market
- **Russian law compliance:** ad markup via ORD (ERID token), medical ad warnings
- **Verticals:** dental clinics, beauty salons, restaurants, EdTech, fitness, B2B services, local stores

## Real cases

| Case | Result | What we did |
|---|---|---|
| Dental clinic, Pokrovka, Moscow | 12 → 47 weekly leads in 6 weeks | Recon → "fixed price before treatment" positioning → landing rewrite → Yandex Direct copy → welcome email sequence |
| **MEDEA Dent** · dental, Moscow | leads ×3.4 in 90 days | Hero with real doctors instead of stock testimonials, transparent pricing, FAQ closing 6 objections |
| **Simbios Marketing** · agency, Moscow | conversion +58% in 60 days | Killer headline "13,500 drivers for taxi fleets at 1,800 RUB per lead" instead of abstractions |

## Articles

Detailed walkthroughs of each agent and methodology:

- [Claude for marketing: 21 agents replacing one marketer](https://telegra.ph/Claude-dlya-marketinga-21-gotovyj-agent-vmesto-odnogo-marketologa-05-03)
- [Claude Skills explained: why they're killing prompt-channel Patreons](https://telegra.ph/Claude-Skills-chto-ehto-i-pochemu-oni-ubivayut-rynok-prompt-kanalov-na-Patreon-05-03)
- [Marketing without a marketer: step-by-step system](https://telegra.ph/Kak-sdelat-marketing-bez-marketologa-21-AI-agent-v-Claude-vmesto-otdela-za-100Kmes-05-03)
- [AI for dental clinics: real case 12 → 47 leads in 6 weeks](https://telegra.ph/AI-dlya-stomatologii-realnyj-kejs-12--47-zayavok-za-6-nedel-bez-agentstva-05-03)
- [Schwartz awareness levels: 5 levels that change everything in copywriting](https://telegra.ph/Urovni-osoznannosti-po-SHvartcu-5-urovnej-kotorye-menyayut-vsyo-v-kopirajtinge-05-03)
- [Email with AI: 5-email welcome sequence in 30 minutes](https://telegra.ph/Email-rassylka-s-AI-welcome-seriya-iz-5-pisem-za-30-minut-05-03)
- [Claude Code on Windows: 3 install methods in 10 minutes](https://telegra.ph/Claude-Code-na-Windows-3-sposoba-ustanovki-za-10-minut-05-03)

**Video walkthrough (Russian):** [youtube.com/watch?v=UrU_tapUIxM](https://www.youtube.com/watch?v=UrU_tapUIxM)

## Pricing tiers

This open-source version is the first of three:

| Tier | What | Price |
|---|---|---|
| 🆓 **Free** (this repo) | 21 skills locally, your API key | $0 |
| 💼 **Hosted** ([app.natashabrovkina.com](https://app.natashabrovkina.com)) | UI, brand memory, team mode, no API key needed | 2,990 RUB/mo (~$33) |
| 🤝 **With me** ([Telegram @NATASHABROVKINA](https://t.me/NATASHABROVKINA)) | I personally build for you in 30 days | 49,000 RUB (~$540) |

## Contributing

Pull requests welcome. Especially:
- New showcase cases (real business, real numbers)
- Adaptations for other markets (Belarus, Kazakhstan, Georgia)
- Localization for English-speaking markets
- More business types in `BUSINESS_TYPES`

Issues too — bug reports or new agent proposals.

## Author

**Natalia Brovkina** · founder, AI Marketing Studio
- 🌐 Website: [natashabrovkina.com](https://natashabrovkina.com)
- 💬 Telegram: [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- 🎥 YouTube: [@NateBrovk](https://youtube.com/@NateBrovk)
- 🐙 GitHub: [@nibrovkina-cyber](https://github.com/nibrovkina-cyber)

## License

[MIT](../LICENSE) — fork it, adapt to your brand, share changes back. For commercial use, please leave attribution: "Powered by natashabrovkina.com" or a link to this repo.

## Star this repo

If you got it running — **give it a ⭐.** It helps other entrepreneurs find it.

If something didn't work — open an [issue](https://github.com/nibrovkina-cyber/natalia-marketing-department/issues), I respond within a day.
