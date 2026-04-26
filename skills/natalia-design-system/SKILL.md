---
name: natalia-design-system
description: Дизайн-система natashabrovkina.com — токены, типографика, компоненты, layout-правила. Извлечена из Claude Design v2. Используется любым агентом который генерит HTML/CSS (carousel, motion, landing, ad creative).
version: 1.0.0
---

# natalia · design system

**Foundation skill для всего визуального вывода.** Любой natalia-* агент который генерит HTML, изображения или layout — должен следовать этому файлу.

## Палитра — два режима

### `data-palette="warm"` (default, modern AI 2026)
```css
--bg: #F7F4EE;          /* off-white cream фон */
--bg-card: #FBF9F4;     /* светлая карточка */
--surface: #EFEAE0;     /* глубокая cream */
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

**Правило:** **один accent на экран.** Primary CTA, link hover, inline emphasis. Никогда не в body copy.

## Шрифты (Google Fonts)

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:ital,wght@1,400;1,500;1,600&family=JetBrains+Mono:wght@400;500&display=swap">
```

| Назначение | Шрифт | Веса |
|---|---|---|
| Headlines / UI / body | Inter | 400, 500, 600, 700 |
| Italic accent words | Playfair Display Italic | 500 |
| Mono / kickers / prices | JetBrains Mono | 400, 500 |

## Типографическая шкала

| Уровень | Размер | Line-height | Letter-spacing | Вес |
|---|---|---|---|---|
| Display | 96px | 0.95 | -0.035em | 600 |
| H1 | 64px | 1.0 | -0.03em | 600 |
| H2 | 40px | 1.05 | -0.02em | 600 |
| H3 | 24px | 1.2 | -0.01em | 600 |
| Body | 17px | 1.55 | — | 400 |
| Small | 14px | 1.5 | — | 400 |
| Mono kicker | 11px | — | 0.14em uppercase | 500 |

**Italic accent rule:** одно Playfair italic слово внутри Inter headline. Никогда не целый h1 в Playfair.

```html
<h1>Готова <em class="italic-display">удвоить</em> выручку?</h1>

<style>
.italic-display {
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-weight: 500;
  letter-spacing: -0.01em;
}
</style>
```

## Spacing

| Контекст | Desktop | Mobile |
|---|---|---|
| Между секциями | 60-120px | 40-60px |
| Padding страницы | 48-64px | 24px |
| Padding карточки | 28-48px | 20px |
| Между h1 и subhead | 24-32px | 16px |

## Border-radius

- Default: **0 (sharp)** — modern AI 2026 эстетика
- Допустимо: 14-22px на mobile-карточках или image-блоках
- Никогда: rounded-full pill-кнопки с gradient (запрет)

## Компоненты

### Button (4 variants)

```html
<!-- Primary (default ink) -->
<button class="btn btn-primary">Попробовать бесплатно <span class="arr">→</span></button>

<!-- Accent (orange CTA) -->
<button class="btn btn-accent">Записаться · 3 места <span class="arr">→</span></button>

<!-- Ghost (outline) -->
<button class="btn btn-ghost">Посмотреть метод</button>

<!-- Link (underline) -->
<button class="btn btn-link">Читать кейсы <span class="arr">→</span></button>

<style>
.btn {
  font-family: 'Inter', sans-serif;
  font-size: 15px;
  font-weight: 500;
  letter-spacing: -0.005em;
  padding: 14px 22px;
  border: 1px solid transparent;
  border-radius: 0;
  cursor: pointer;
  transition: transform .15s ease, background .2s ease;
  display: inline-flex;
  align-items: center;
  gap: 10px;
}
.btn-primary { background: var(--ink); color: var(--bg); }
.btn-primary:hover { background: var(--accent); color: var(--accent-ink); }
.btn-accent { background: var(--accent); color: var(--accent-ink); }
.btn-accent:hover { filter: brightness(.93); }
.btn-ghost { background: transparent; color: var(--ink); border-color: var(--hairline); }
.btn-ghost:hover { border-color: var(--ink); }
.btn-link { background: transparent; padding: 14px 0; border: 0; border-bottom: 1px solid var(--ink); }
.btn-link:hover { color: var(--accent); border-color: var(--accent); }
.btn .arr { transition: transform .2s ease; }
.btn:hover .arr { transform: translateX(3px); }
</style>
```

### Tag (kicker / risk-reversal)

```html
<span class="tag">3 ТАРИФА · ОТ 0 ₽</span>
<span class="tag accent"><span class="dot"></span>3 ЛЕНДИНГА БЕСПЛАТНО</span>

<style>
.tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  padding: 6px 10px;
  border: 1px solid var(--hairline);
  color: var(--ink-2);
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
.tag.accent { background: var(--accent-soft); border-color: var(--accent); color: var(--accent); }
.tag .dot { width: 6px; height: 6px; background: var(--accent); border-radius: 50%; }
</style>
```

### Pricing card

См. полный паттерн в [PricingCard.tsx](../../app/components/ui/PricingCard.tsx) проекта `ai-marketing-natalia`. Структура:
- Roman numeral (I/II/III) + tier name (mono uppercase)
- Tier display name (Inter 26 + optional `.italic-display` accent)
- "Who it's for" description
- Big price (Inter 56-72 tabular-nums) + unit (mono)
- Billing line
- Features list (numbered, no ✓)
- CTA (primary/accent/ghost)
- Fineprint

### Section head

Eyebrow + h2 + right-aligned description:

```html
<div class="section-head">
  <div>
    <div class="eyebrow">/ ТАРИФЫ</div>
    <h2>Три способа <em class="italic-display">работать</em> со мной</h2>
  </div>
  <p class="section-desc">Каждый тариф решает разную задачу.</p>
</div>
```

### Pull-quote

```html
<blockquote class="pull-quote">
  «Первое впечатление — единственное.»
  <cite>— David Ogilvy, 1963</cite>
</blockquote>

<style>
.pull-quote {
  border-left: 3px solid var(--accent);
  padding-left: 32px;
  font-family: 'Playfair Display', serif;
  font-style: italic;
  font-size: clamp(22px, 2.4vw, 34px);
  line-height: 1.4;
  letter-spacing: -0.01em;
  font-weight: 500;
  margin: 80px 0;
}
</style>
```

## Animation

- Subtle scroll-reveal (opacity 0 → 1 + translateY 24 → 0)
- Hover-lift на карточках: translateY(-2px)
- Pulse на dot-индикаторах (2.6s ease-in-out)
- **Никаких parallax, никаких сложных gradient-mesh**

## Запреты (повтор для важности)

❌ Pill-кнопки с purple/blue градиентом
❌ ✓ галочки в feature-листах
❌ «Most Popular» badge
❌ Stat-strip «47 млн / 20 / 16» в hero
❌ Зачёркнутая цена со стрелкой
❌ Editorial drop-cap
❌ Playfair для целого headline
❌ Card-grid 1:1 для тарифов (используй table-style 3 столбца)
❌ Эмодзи в заголовках

## Использование в других skills

Когда natalia-carousel / natalia-motion / natalia-webdesign / любой генератор HTML генерит вывод:

1. Прочитай этот файл первым
2. Загрузи Google Fonts link
3. Используй CSS-переменные палитры (warm по default)
4. Применяй `.italic-display` только на 1 слово в headline
5. Sharp corners (radius 0)
6. Один accent на экран
7. JetBrains Mono для mono-моментов (kickers, цены, метаданные)
