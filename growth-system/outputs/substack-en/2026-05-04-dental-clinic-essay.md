# A Moscow dentist, 47 weekly leads, and 21 markdown files

*How a one-dentist clinic with no marketing budget grew 4x in 6 weeks — by replacing what would have been a marketing department with 21 open-source AI agents.*

---

## I.

The dentist had 12 leads a week.

Twelve. In a city of 12 million people. Walking distance to three metro stations. A clean clinic, two assistants, a dentist with twenty years of experience, transparent prices, real reviews. Twelve leads.

He did the things you're supposed to do. Yandex.Direct ads, a templated landing page, a Telegram channel he updated when he remembered. The website said "quality treatment, individual approach, modern equipment." Same as every dental clinic in Moscow, which is to say, same as every dental clinic in any city — there's only one copywriter for small business and they only know three sentences.

He couldn't hire a marketer. A marketer in Moscow costs 200,000 rubles a month — about $2,200, which is roughly the entire monthly revenue of his clinic on a slow week. He couldn't hire an agency either; agencies start at 150,000 rubles for the first deliverable and go up from there. Most dental clinics in Russia are in the same position. They watch their competitors do exactly nothing better than they do, and they know the only difference is who happens to rank higher in Yandex this week.

So he asked me what I'd do. I said: give me six weeks and don't change anything else.

---

## II.

The first thing I did was open Claude Code and run `/natalia-competitors`.

Claude Code is Anthropic's terminal client — free, runs locally, talks to your files. The skills I run on it are mine: a folder of 21 markdown files I spent six months building, each one teaching Claude how to do one specific marketing task by the methodology of three classics — Ogilvy, Schwartz, Hopkins.

`/natalia-competitors` is the first one you run for any new client. It pulls three to five competitors within walking distance, opens their websites in a headless browser, scrapes the copy, the prices, the testimonials, the team page if there is one, and analyzes them along seven axes: positioning, pricing, audience, weaknesses, strengths, content, conversion mechanics.

For the dentist on Pokrovka it returned three competitors. All three said "quality treatment." All three published prices as "from X rubles" — the classic dental dark pattern: list a low entry price, escalate the bill once the patient is in the chair. None of them locked the price in writing before treatment.

This was the gap.

Patients of dental clinics are scared of two things: pain and being scammed on price. The first one is medical and you can't really sell against it (you can promise comfort, but only with proof). The second one is structural. Every patient has been told "you also need a crown, that's an extra 30,000 rubles" while they're already partially numbed and emotionally committed. Every patient has felt that betrayal once. Patients walk into clinics already braced for it.

If you're the only clinic in walking distance that says, plainly, in the headline: *price locked before treatment starts* — and means it, contractually — you become the safe choice. You don't have to be cheaper. You don't have to be more famous. You have to be the one that doesn't look like a trap.

I ran `/natalia-positioning` and the output, which is just Claude reasoning out loud through Schwartz and Ogilvy frameworks, came back with the angle in plain Russian: *Цена зафиксирована до начала лечения. Никаких скрытых платежей.* Price locked before treatment starts. No hidden charges. The dentist read it and said: "I already do that. I just never put it on the website."

That's the whole bug, isn't it. Most small-business websites are silent on the things that would make a stranger trust them.

---

## III.

The next two weeks were execution.

`/natalia-landing` rewrote the first screen and the pricing block. The old hero said *Качественная стоматология в Москве* — quality dentistry in Moscow. The new one said *Цена зафиксирована до начала лечения. Бесплатный осмотр.* Below it, an actual price list — five common procedures, each with a concrete locked number, not a "from X." That's a small change with strange consequences. I've watched real dentists balk at it. They'll tell me locking prices is impossible because complications happen. I'll tell them complications can be a separate, also priced line. They'll tell me their colleague does it differently. I'll tell them their colleague has the same 12 leads a week.

`/natalia-ads` rewrote the Yandex.Direct copy. The old ad said *Качественная стоматология в центре Москвы. Звоните!* — Quality dentistry in central Moscow. Call now. Ten words, zero specifics, every dental clinic in Moscow had run that exact ad at some point in the last decade, the algorithm had learned to bury it. The new ad said *Зафиксированная цена до лечения. Бесплатный осмотр. Покровка.* Locked price before treatment. Free consultation. Pokrovka. Same length, every word doing work. CTR went from 2.1% to 4.8% within a week. Cost per lead dropped from 2,400 rubles to 980. None of this is magic. It's that if you say something specific in an ad, more people click.

`/natalia-email` was the one that surprised the dentist most. He'd been losing two-thirds of the people who booked the free consultation — they'd schedule it on a Tuesday, talk themselves out of it by Thursday, ghost on Friday. He didn't have an email sequence; he had no automation at all. We wrote five emails — sent on day 0, day 1, day 3, day 5, day 7 — and the only thing the emails did was reduce anxiety. Day 1 said: "We won't do anything at the consultation, we'll just look. You can leave at any point." Day 3 was three real testimonials from patients with the same kind of problem the new patient probably had. Day 5 answered the three things every new dental patient is afraid to ask: will it hurt, can I pay in installments, what if I need more than one visit. Day 7 was a single line saying we kept their slot but would happily move it.

Booking-to-show-up went from 32% to 51% in the first month.

That's the part that compounds. The ads brought more leads. The landing converted more of them into bookings. The emails actually got those bookings into the chair. Each step lifted the next. By week six, 12 leads a week had become 47.

---

## IV.

I'm pre-revenue on the hosted version of this. There's a website, natashabrovkina.com, where eventually you'll be able to log in and run all 21 skills against your business through a UI without dealing with Claude Code or API keys, but it's launching this summer. Right now what exists is the GitHub repo: 21 SKILL.md files, a master orchestrator skill called `natalia` that knows about all of them, and a methodology folder that explains the three classics underneath.

It's MIT-licensed. Free. You clone the repo, you copy the `skills/` folder into `~/.claude/skills/`, you run `/natalia-positioning` in Claude Code, and you have a strategic brief in 15 minutes. The whole thing costs $5-30 a month on Anthropic API depending on how much you use it. One client brief is about $0.30. A full landing page rewrite is $1-2. The 21 agents themselves are free forever.

Why open-source? Two reasons.

First, audience-building before revenue. I don't have a list yet. I don't have credibility yet. The hosted product won't have customers if no one trusts the underlying methodology, and methodology is hard to trust if it's hidden behind a paywall. So the methodology is open. Anyone who reads the SKILL.md files can verify that what's inside is actually Schwartz and Ogilvy and Hopkins, applied honestly to specific marketing tasks. The hosted product becomes the convenience layer on top: nicer UI, no API keys, a brand-memory database that persists across sessions, team mode. People who want that pay; people who want to clone the repo and run it locally don't, and that's fine.

Second, distribution. Open-source is a distribution channel. People search for "claude skills marketing" and they find this repo. They search for "ai marketing for small business in russia" and they find the articles I publish from it. They fork the repo for their own niche — there are people now adapting it for B2B SaaS, for legal services, for fitness studios. Every adaptation is a marketing channel I didn't have to pay for. This is the playbook Vercel and Supabase and PostHog have been running for a decade. It works.

---

## V.

What I learned from the dentist case, more than anything, is how much of small-business marketing is a coordination failure.

The dentist already locked prices for his patients in person. He just didn't put it on the website. He already had warm testimonials from grateful patients. He just didn't email them to new patients. He already explained the consultation procedure to every walk-in. He just didn't put that explanation in an automated email sequence. The marketing team he didn't have wasn't the bottleneck — the *artifacts* of a marketing team were the bottleneck. The website. The ads. The emails. The places where his real clinic met a stranger online.

What 21 markdown files do is generate those artifacts. They don't replace strategic thinking — the dentist is still the one who decides what services to add, what hours to keep, what kind of clinic to be. They replace the production layer between strategy and the public. The part where you have to write copy, design landing blocks, sequence emails, draft ad variations, set up A/B tests. That production layer is 90% of what a marketing team does for a small business, and 80% of it is mechanical once the methodology is right.

The methodology can't be skipped. ChatGPT-with-good-prompts is not a substitute for this. ChatGPT will write you "quality treatment" copy on default settings, because the average of internet writing about dental clinics is "quality treatment" copy. You have to teach the AI which 1923 book to apply, what awareness level the audience is on, which specific verifiable claims to substitute for adjectives. That teaching is what the SKILL.md files do. They're not prompts. They're the methodology written down once, then applied a thousand times across every client without re-explaining.

This is the part that makes me think open-source AI tooling is going to eat a lot of small-business marketing services in the next two years. Not the high-end strategy work. Not the personal brand-building of founders. The middle layer — the production work that costs 100K rubles a month and exists because somebody had to physically write the copy. That layer is going to be a folder of markdown files most people clone from GitHub.

---

## VI.

If you have a small business and a website you suspect says "quality service" — or its local equivalent — try this experiment. Run `/natalia-positioning` against your URL. The skill costs about $0.30 in API tokens. It'll tell you in fifteen minutes what you'd pay an agency 50,000 rubles to tell you in two weeks. Whether you act on the output is up to you, but you'll know the answer.

The repo is at github.com/nibrovkina-cyber/natalia-marketing-department. MIT license, 21 agents, free. Hosted version is at natashabrovkina.com — waitlist is open, launches this summer.

If you're a marketer reading this and worried I'm devaluing your craft: I'm not. The methodology is harder than ever; the production is easier. What this changes is who can afford to do marketing right. A dentist on Pokrovka used to need a $2,200/month marketer to grow from 12 leads to 47. Now he needs $5 of Anthropic credits and an afternoon. That's a rounding error against his revenue. Multiply that across the 5 million small businesses in Russia that can't afford a marketer today, and the question stops being whether AI replaces marketers and starts being whether anyone gets to keep watching small businesses lose to "quality service" forever.

I don't want to. So I open-sourced the fix.

---

*Subscribe for the next essay. I write about the intersection of AI tooling, direct response copywriting, and small-business marketing in Russia and beyond. Roughly one essay per week.*

*All examples in this piece are real, with verifiable numbers. If you want to verify, the dental clinic case lives at telegra.ph (linked in the next email). The Telegram channel for the clinic is public.*
