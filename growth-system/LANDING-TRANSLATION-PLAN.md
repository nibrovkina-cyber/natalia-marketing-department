# Landing translation plan — natashabrovkina.com → EN

## Текущий статус

✅ **Tool полностью переведён:** все 22 SKILL.md в `skills-en/` (top translator quality, native EN copy, не machine translation).

✅ **Gallery data переведён:** `content/gallery.en.json` — case studies для MEDEA Dent + Simbios на английском с переведёнными методологическими сносками.

✅ **README EN:** `docs/README.en.md` — full English version для глобальной GitHub-аудитории.

⏳ **Сами landing-страницы (app/*/page.tsx) — на русском.** Это ~5000 строк JSX с inline русскими строками. Перевод требует separate session с фокусом.

---

## Архитектурный выбор для landing i18n

Три варианта реализации EN-версии:

### Вариант 1 — Next.js i18n с `[locale]` сегментом (рекомендую)

**Что делать:**
1. Reorganize `app/` → `app/[locale]/`
2. Add middleware.ts для locale-detection (Accept-Language header → /ru/ или /en/)
3. Add language switcher component в SiteNav
4. Each page принимает `params: { locale }` и читает из dictionaries

**Структура:**
```
app/
├── [locale]/
│   ├── page.tsx            # / + /en/ + /ru/
│   ├── method/page.tsx
│   ├── pricing/page.tsx
│   ├── tool/page.tsx
│   ├── waitlist/page.tsx
│   └── gallery/page.tsx
├── api/                    # API routes без locale
├── components/
└── layout.tsx
content/
├── dictionaries/
│   ├── en.json             # все строки EN
│   └── ru.json             # все строки RU
```

**Плюсы:** проперти Next.js i18n, SEO-friendly (отдельные URL), один JSX, два языка.

**Минусы:** ~6 часов рефакторинга. Все existing routes ломаются (нужны redirects).

### Вариант 2 — Параллельная директория `app/en/` (быстрее, проще)

**Что делать:**
1. Copy `app/page.tsx` → `app/en/page.tsx` с переведёнными strings
2. Same для /method, /pricing, /tool, /waitlist, /gallery
3. Add language switcher в SiteNav
4. Default `/` остаётся RU

**Структура:**
```
app/
├── page.tsx            # RU homepage
├── method/page.tsx     # RU method
├── ...
└── en/
    ├── page.tsx        # EN homepage
    ├── method/page.tsx # EN method
    └── ...
```

**Плюсы:** ~2 часа. No breaking changes. Existing /method etc продолжают работать.

**Минусы:** maintenance debt — каждое изменение копий двойное. Но для MVP-стадии ок.

### Вариант 3 — Отдельный домен natalia-md.io (overkill)

Запустить параллельный EN-сайт на отдельном Vercel проекте. Слишком много инфраструктуры для текущей стадии.

**Не рекомендую сейчас.**

---

## Рекомендация — Вариант 2 поэтапно

Pre-launch (sprint 1, ~2 часа):
1. `app/en/page.tsx` — homepage с EN-копией
2. `app/components/LanguageSwitcher.tsx` — RU/EN toggle в SiteNav
3. `app/en/layout.tsx` — metadata wrapper (canonical, OG, locale en_US)

Post-launch (sprint 2, ~2 часа):
4. `app/en/method/page.tsx` — методология (наибольший evergreen-контент)
5. `app/en/pricing/page.tsx` — pricing с USD-конвертацией
6. `app/en/gallery/page.tsx` + `[slug]` — кейсы (читать из gallery.en.json)

Sprint 3 (~1 час):
7. `app/en/waitlist/page.tsx` — форма с EN-копией
8. `app/en/tool/page.tsx` — Студия (большая страница, переведём в последнюю очередь, т.к. /tool требует Anthropic API balance чтобы реально работать)

---

## Принципы перевода (top translator quality)

### НЕ дословно

Russian original: «Маркетинг по Огилви. Запускает один человек.»
Bad direct: "Marketing by Ogilvy. Runs by one person."
Good native: "Ogilvy-grade marketing. From a team of one."

### Сохраняем

- Имена методологий (Ogilvy/Schwartz/Hopkins) — без перевода
- Названия кейсов (MEDEA Dent, Simbios Marketing) — без перевода
- Цифры (×3.4, +58%, 90 days) — без перевода
- Brand voice (Kinfolk-editorial, не SaaS) — переносится тонально
- "ты"/"you" — casual addressing, не formal "thou"

### Адаптируем

- Цены: рубли → доллары (1₽ ≈ $0.011, округлять до $5/$10/$50/$100)
- Каналы: Яндекс.Директ → Google Ads (с упоминанием "Russia: Yandex.Direct")
- ЮKassa → Stripe
- Маркировка ОРД — отдельная секция "If you're publishing in Russia, Russian advertising-mark applies (ERID)"

### Voice rules

- Active voice > passive
- Sentence-level rhythm: short / short / longer
- Numbers in first half of sentence
- "Marketing department in a markdown file" — типа этого, прямо
- Никаких "We are excited to announce" / "leverage" / "synergy"

---

## Тестовый перевод hero (для homepage app/en/page.tsx)

```tsx
<h1>
  Ogilvy-grade marketing.
  <span style={{ display: "block", fontStyle: "italic" }}>
    From a team of one.
  </span>
</h1>
<p>
  21 AI agents on Ogilvy / Schwartz / Hopkins methodology.
  They do the work of a copywriter, designer, SEO, and ads strategist —
  all at once.
</p>
<button>Download free on GitHub →</button>
<button>Open hosted Studio →</button>
<small>No signup · first 3 landings free</small>
```

vs. оригинал RU:
```tsx
<h1>
  Маркетинг по Огилви.
  <span>Запускает один человек.</span>
</h1>
<p>
  16 AI-агентов на методологии Ogilvy, Schwartz и Hopkins.
  Работают за копирайтера, дизайнера, SEO и таргетолога —
  одновременно.
</p>
<button>Скачать бесплатно на GitHub →</button>
<button>Открыть hosted-инструмент →</button>
<small>без регистрации · первые 3 лендинга бесплатно</small>
```

---

## Что нужно от Натальи перед стартом перевода landing

1. **Решение по варианту:** 1 (proper i18n) vs 2 (параллельная app/en/)
2. **Согласовать ценообразование на EN:**
   - Free: open-source GitHub (везде одинаково)
   - Self-Serve: 2 990 ₽/мес → ~$30/мес?
   - Personal: 49 000 ₽ → ~$540?
3. **Брендинг "natashabrovkina.com" → English:** оставлять "Natalia Brovkina" или адаптировать?
4. **Целевая EN-аудитория:** US-only или global (US + UK + EU)?

После этих ответов — следующий sprint можно пройти за 2 часа.

---

## Что я сделала автономно

- ✅ Все 22 SKILL.md в `skills-en/` (полная EN-версия инструмента)
- ✅ `content/gallery.en.json` (case-study данные)
- ✅ `docs/README.en.md` (EN README репо)
- ✅ Этот документ-стратегия

Что осталось требует архитектурного решения. Не делаю автономно потому что:
1. Refactor под i18n меняет URLs существующего сайта (breaking change)
2. Цены USD требует решения (моя оценка может быть неоптимальной)
3. Брендинг — твоё решение
