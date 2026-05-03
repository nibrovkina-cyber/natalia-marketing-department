# SEO-чеклист — natashabrovkina.com + natalia-marketing-department

Состояние на 2026-05-03. Что сделано, что осталось, что критично.

---

## ✅ Что уже готово (autonomous, без участия Натальи)

### Site (ai-marketing-natalia → natashabrovkina.com)

| Элемент | Статус | Где |
|---|---|---|
| Sitemap.xml | ✅ Динамический, включает gallery slugs | [app/sitemap.ts](../../ai-marketing-natalia/app/sitemap.ts) |
| Robots.txt | ✅ Allow для AI-краулеров (GPTBot, ClaudeBot, PerplexityBot, CCBot) | [app/robots.ts](../../ai-marketing-natalia/app/robots.ts) |
| JSON-LD Person | ✅ Schema.org Person с sameAs (Telegram, GitHub) | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |
| JSON-LD Organization | ✅ legalName, areaServed, logo, founder | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |
| JSON-LD SoftwareApplication | ✅ С тремя Offer (Free/Self-Serve/Personal) | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |
| OpenGraph default | ✅ ru_RU locale | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |
| Twitter Card | ✅ summary_large_image | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |
| OG-image dynamic | ✅ Генерируется через `/opengraph-image.tsx` | [app/opengraph-image.tsx](../../ai-marketing-natalia/app/opengraph-image.tsx) |
| Per-page metadata: / | ✅ Добавлено 2026-05-03 (canonical, keywords, OG) | [app/page.tsx](../../ai-marketing-natalia/app/page.tsx) |
| Per-page metadata: /tool | ✅ Добавлено 2026-05-03 через layout-обёртку | [app/tool/layout.tsx](../../ai-marketing-natalia/app/tool/layout.tsx) |
| Per-page metadata: /gallery | ✅ Добавлено 2026-05-03 через layout-обёртку | [app/gallery/layout.tsx](../../ai-marketing-natalia/app/gallery/layout.tsx) |
| Per-page metadata: /pricing | ✅ Уже было | [app/pricing/page.tsx](../../ai-marketing-natalia/app/pricing/page.tsx) |
| Per-page metadata: /method | ✅ Уже было | [app/method/page.tsx](../../ai-marketing-natalia/app/method/page.tsx) |
| Per-page metadata: /waitlist | ✅ Уже было | [app/waitlist/page.tsx](../../ai-marketing-natalia/app/waitlist/page.tsx) |
| Cyrillic font subset | ✅ Inter + Playfair с cyrillic | [app/layout.tsx](../../ai-marketing-natalia/app/layout.tsx) |

### GitHub repo (natalia-marketing-department)

| Элемент | Статус |
|---|---|
| README с keywords-rich заголовком | ✅ Обновлён 2026-05-03 |
| README с EN-описанием для глобальных GitHub-поисковиков | ✅ Добавлено |
| Badges (License, Claude Skills, SMB) | ✅ Добавлено |
| Showcase кейсы с цифрами | ✅ Уже было |
| Ссылки на 7 опубликованных Telegraph-статей | ✅ Добавлено |
| Корректная YouTube-ссылка @NateBrovk | ✅ Исправлено |
| Skills count: 21 (вместо устаревшего 16) | ✅ Исправлено |

### Off-site контент (Telegraph)

| Статья | Статус |
|---|---|
| Claude для маркетинга | ✅ Опубликовано |
| Claude Skills что это | ✅ Опубликовано |
| Маркетинг без маркетолога | ✅ Опубликовано |
| AI для стоматологии | ✅ Опубликовано |
| Schwartz уровни осознанности | ✅ Опубликовано |
| Email рассылка с AI | ✅ Опубликовано |
| Claude Code установка Windows | ✅ Опубликовано |

URL list: [growth-system/inputs/published-urls.md](inputs/published-urls.md)

---

## 🔴 Что требует Наталью (нельзя сделать автономно)

### Приоритет 1 — после покупки домена

| Задача | Где | Время |
|---|---|---|
| Зарегистрировать сайт в **Yandex Webmaster** → подтвердить владение → добавить sitemap | https://webmaster.yandex.ru/ | 15 мин |
| Зарегистрировать сайт в **Google Search Console** → подтвердить через DNS TXT или meta tag → добавить sitemap | https://search.google.com/search-console | 15 мин |
| Зарегистрировать в **Bing Webmaster Tools** (для Bing/IndexNow) | https://www.bing.com/webmasters | 5 мин |
| Зарегистрировать в **IndexNow** → API-ключ положить в `.well-known/` файл | https://www.indexnow.org/ | 10 мин |
| Submit sitemap.xml в каждом из 3 webmaster-tools | — | 5 мин |
| Установить **Yandex.Metrica** счётчик → добавить тег в `app/layout.tsx` | https://metrika.yandex.ru/ | 15 мин (Наталья создаёт счётчик, я добавляю код) |

### Приоритет 2 — GitHub SEO (требует gh CLI или ручного UI)

| Задача | Время |
|---|---|
| Открыть https://github.com/nibrovkina-cyber/natalia-marketing-department/settings → **Topics** добавить: `claude-skills`, `claude-code`, `ai-marketing`, `marketing-automation`, `direct-response`, `russian-marketing`, `ogilvy`, `schwartz`, `hopkins`, `open-source-marketing`, `claude-ai`, `ai-agents` | 5 мин |
| **Description** репо обновить: `21 Claude Skills replacing a marketing department for Russian small business · MIT · Schwartz/Ogilvy/Hopkins methodology` | 1 мин |
| **Website** в About: `https://natashabrovkina.com` | 1 мин |
| Проверить `Releases` — создать v1.0.0 release с changelog (помогает discoverability) | 10 мин |

### Приоритет 3 — Off-site SEO

| Задача | Где | Время |
|---|---|---|
| Запостить репо на **Habr/news** с пометкой "open source" | https://habr.com/ru/news/ | 15 мин |
| Запостить на **vc.ru** (когда разблокируют коммерческий аккаунт) | — | — |
| Submit в **Awesome Claude Skills** на GitHub (есть awesome-list) | https://github.com/topics/claude-skills | 5 мин |
| Опубликовать на **ProductHunt** (когда инструмент сайта заработает) | https://producthunt.com | 30 мин |
| Submit на **Reddit r/ClaudeAI**, **r/marketing** | — | 10 мин |

---

## 🟡 Что можно улучшить (low priority, поэтапно)

### Site

- [ ] FAQPage Schema на `/method` — каждый блок методологии как FAQ
- [ ] BreadcrumbList Schema на `/gallery/[slug]` (Главная → Кейсы → MEDEA Dent)
- [ ] Article Schema на каждом кейсе в `/gallery/[slug]` с datePublished
- [ ] Hreflang теги для en (когда сделаем EN-версию)
- [ ] PWA-манифест (`manifest.webmanifest`)
- [ ] Lazy-loading для картинок в `/gallery`
- [ ] Image alt-теги на всех картинках в `/gallery/[slug]` — критично для Yandex Images
- [ ] Внутренние ссылки между кейсами (related cases)

### Repo

- [ ] CONTRIBUTING.md с структурой
- [ ] CODE_OF_CONDUCT.md (минимальный)
- [ ] GitHub Wiki или /docs с подробной документацией каждого skill
- [ ] EN-версия README в `/docs/README.en.md`
- [ ] Release tags по semver: v1.0.0, v1.1.0 etc

### Off-site

- [ ] Перепостить 7 Telegraph-статей в **Дзен** (с уникальными обложками)
- [ ] Cross-post на **Substack** для EN-аудитории (есть [substack-en.md](../../ai-marketing-natalia/content/substack-en.md))
- [ ] LinkedIn long-form (есть [linkedin-en-longform.md](../../ai-marketing-natalia/content/linkedin-en-longform.md))
- [ ] Submit в [Show HN](https://news.ycombinator.com/show) — есть готовый [show-hn-submission.md](../../ai-marketing-natalia/content/show-hn-submission.md)
- [ ] Гостевой пост на **Habr/companies** в ~5 разделах

---

## 📊 Метрики которые отслеживать

### Технические (раз в неделю)

| Метрика | Где смотреть | Норма для нового сайта |
|---|---|---|
| Yandex/Google indexed pages | Webmaster Search Console | Все 6 + кейсы за 7-14 дней |
| Core Web Vitals (LCP, INP, CLS) | PageSpeed Insights | LCP < 2.5s, INP < 200ms, CLS < 0.1 |
| Mobile usability errors | Search Console | 0 |
| Crawl errors | Search Console | 0 |

### Поисковый трафик (раз в месяц)

| Метрика | Где |
|---|---|
| Impressions / Clicks | Yandex Webmaster + Google Search Console |
| Топ-10 ключевых запросов | Search Console "Performance" |
| CTR (impressions → clicks) | Search Console |
| Средняя позиция в выдаче по топ-ключам | Search Console |

### Off-site (раз в неделю)

| Метрика | Где |
|---|---|
| GitHub stars | github.com/nibrovkina-cyber/natalia-marketing-department/stargazers |
| GitHub traffic (clones, visitors) | github.com/.../insights/traffic |
| Telegraph просмотры | Не отслеживаются (минус Telegraph) |
| Habr статья просмотры | habr.com/ru/users/[username]/articles |
| Дзен статья просмотры | dzen.ru/profile/editor (статистика) |

---

## 🎯 Ключевая стратегия SEO для natalia-marketing-department

### Топ-7 целевых запросов

| Запрос | Конкуренция | Приоритет публикации |
|---|---|---|
| "claude для маркетинга" | low | Telegraph + vc.ru/Habr (transactional) |
| "claude skills что это" | low | Telegraph + Habr (informational) |
| "как сделать маркетинг без маркетолога" | low | Telegraph + Дзен (transactional) |
| "AI для стоматологии маркетинг" | medium | Telegraph + Дзен + специализированные сайты |
| "методология Schwartz уровни осознанности" | low | Telegraph (educational) |
| "email рассылка с AI" | medium | Telegraph + Habr |
| "claude code установка windows" | low | Habr (главный) + Telegraph (поддерживающий) |

### Принципы линкинга

- **Каждая Telegraph-статья** ссылается на **GitHub-репо** + **YouTube-видео** + **natashabrovkina.com/waitlist**
- **README репо** ссылается на все 7 Telegraph-статей и YouTube
- **Кейсы на /gallery** ссылаются на **/method** и **/tool**
- **/method** ссылается на конкретные кейсы как доказательства
- **YouTube описание** ссылается на сайт + GitHub + Telegraph

Это создаёт **связный link graph** — сильный SEO-сигнал.

---

## 🧠 GEO / AEO (Generative Engine Optimization)

С 2025 года ChatGPT, Claude, Perplexity, Gemini становятся каналом трафика. Нужно чтобы AI правильно цитировали:

| Что | Зачем | Статус |
|---|---|---|
| robots.txt allow GPTBot/ClaudeBot/PerplexityBot/Google-Extended | Чтобы AI могли индексировать сайт | ✅ Сделано |
| JSON-LD Person с knowsAbout | Чтобы AI знали в чём ты эксперт | ✅ Сделано |
| Структурированные FAQ на /method | Чтобы AI могли извлекать ответы | ⚠️ Есть текстом, нет FAQPage Schema |
| Уникальные verifiable claims (цифры из кейсов) | AI цитируют то что есть в данных | ✅ ×3.4, +58% — конкретные числа |
| LLMS.txt файл (новая практика 2026) | Прямой манифест для AI о структуре сайта | ❌ Не сделано |

### Создать LLMS.txt

LLMs.txt — простой markdown-файл в корне сайта, описывающий что есть на сайте для AI-краулеров:

```markdown
# natashabrovkina.com — AI Marketing Studio

> Бесплатная open-source альтернатива маркетинговому отделу для малого бизнеса в РФ. 21 Claude Skill + hosted UI.

## Основной продукт
- [Open-source 21 агента](https://github.com/nibrovkina-cyber/natalia-marketing-department) — Claude Skills, MIT
- [Hosted версия](https://natashabrovkina.com/tool) — UI + brand memory, 2990₽/мес (запуск лето 2026)

## Методология
- [Ogilvy / Schwartz / Hopkins](https://natashabrovkina.com/method) — direct response школа

## Кейсы
- [MEDEA Dent](https://natashabrovkina.com/gallery/medea-dent-moscow): ×3.4 заявок за 90 дней
- [Simbios Marketing](https://natashabrovkina.com/gallery/simbios-marketing-moscow): +58% конверсии за 60 дней

## Автор
- [Наталья Бровкина](https://github.com/nibrovkina-cyber) · founder
- Telegram: [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
```

Положить в `ai-marketing-natalia/public/llms.txt`. Эта практика становится стандартом 2026.

---

## Roadmap по неделям

### Неделя 1 (сейчас)
- [x] README SEO-оптимизация
- [x] Per-page metadata для / /tool /gallery
- [x] Все 7 статей на Telegraph
- [ ] Купить домены (Reg.ru) — за тобой
- [ ] Vercel-деплой — после доменов

### Неделя 2 (после деплоя)
- [ ] Yandex Webmaster + Google Search Console + Bing Webmaster
- [ ] Yandex Metrica + Google Analytics 4
- [ ] LLMS.txt в /public/
- [ ] GitHub topics + description + website

### Неделя 3
- [ ] FAQPage Schema на /method
- [ ] BreadcrumbList на /gallery/[slug]
- [ ] Image alt-теги
- [ ] Submit на ProductHunt + Show HN

### Неделя 4-8
- [ ] Cross-post в Дзен / Habr
- [ ] LinkedIn long-form (EN)
- [ ] Substack для EN-аудитории
- [ ] Гостевые посты
- [ ] Анализ через Search Console — что ранжируется, что переписать

---

## Что НЕ делать (anti-patterns)

❌ Покупать ссылки на биржах (Sape, Miralinks, Rotapost) — Google штрафует, Yandex тоже стал
❌ Стуффинг ключевых слов — пишем для людей, не для роботов
❌ Дублирование контента между Telegraph и сайтом — лучше уникальные тексты под каждую платформу или указывать canonical на одну версию
❌ Hidden text / cloaking — мгновенный бан
❌ Создавать 100 Telegraph-страниц с минимальной разницей — Telegraph не SEO-канал, основной — сайт
