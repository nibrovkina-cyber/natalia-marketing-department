# Утренний брифинг — 2026-05-04

Что сделано пока ты спала, что делать сейчас.

---

## ✅ Что готово

### Контент
- **7 статей опубликовано на Telegraph** через автономный API-скрипт ([growth-system/scripts/publish-telegraph.py](scripts/publish-telegraph.py))
- **Все 7 distribution-packs FINAL** с трёхступенчатой воронкой (YouTube → GitHub → waitlist)
- **8 видео-скриптов для серии "Я нагоняю трафик публично"** (Episode 0–7) → [video-series/](video-series/)
- **Episode 0** (анонс) уже было · Episode 1 уже было · **Episode 2-7 написаны этой ночью**
- **Cannell методология (7 Cs + 7 Rs)** в [methodology/cannell-youtube.md](methodology/cannell-youtube.md)

### SEO
- **README** переписан с keyword-rich H1 + 3 badges + EN-summary + 7 Telegraph-ссылок
- **EN README** в [docs/README.en.md](../docs/README.en.md) — для глобальной GitHub-аудитории
- **Per-page metadata** на ai-marketing-natalia: /, /tool, /gallery, /method, /pricing, /waitlist
- **FAQPage Schema** на /method (5 вопросов про Ogilvy/Schwartz/Hopkins → AI будут цитировать)
- **BreadcrumbList Schema** на /gallery/[slug] → улучшит сниппет в Google
- **Article Schema** на /gallery/[slug] → datePublished, author, publisher
- **Image alt-теги** на drag-слайдере /gallery/[slug] (для Yandex Images)
- **llms.txt** в /public/ → новая практика 2026, AI-краулеры (ChatGPT/Claude/Perplexity) знают структуру
- **SEO-чеклист** в [SEO-CHECKLIST.md](SEO-CHECKLIST.md)

### Код / билд
- `ai-marketing-natalia` собирается без ошибок (`npm run build` exit 0, 13 страниц компилируются)
- API endpoints проверены: /api/waitlist работает, /api/chat работает но требует пополнения Anthropic
- **2 локальных коммита** в `natalia-marketing-department`:
  - `1922407` — growth-system пайплайн с 7 статьями
  - `f2cf618` — SEO + методология + Episode 2

---

## 🔴 Что нужно сделать ТЕБЕ когда проснёшься

### Приоритет 1 — финальная оплата

| Где | Что | Сумма |
|---|---|---|
| **Reg.ru** (страница открыта) | Купить domains: natashabrovkina.com + nataliyabrovkina.com + natashabrovkina.ru | ~2200₽/год |
| **console.anthropic.com/settings/billing** | Пополнить депозит для /tool на сайте | $5–30 |

### Приоритет 2 — публикация по подготовленным буферам / открытым окнам

⚠️ **В буфере сейчас текст для Дзен** ("AI стоматология", 6370 символов). Если уже не нужен — скажи мне утром, перезагружу.

| Платформа | Что сделать | Где статус |
|---|---|---|
| **Telegram-канал** | Open Telegram Web → пост 633 символа из буфера → Ctrl+V → опубликовать → закрепить на 24h | окно открыто |
| **Habr** | Открыть [habr.com/ru/articles/edit/draft](https://habr.com/ru/articles/edit/draft/) → заголовок "Claude Code на Windows: 3 способа установки за 10 минут" → markdown-режим → Ctrl+V → хабы (Open source, Программирование, Anthropic, Windows) → опубликовать | окно открыто |
| **Дзен** | Открыть [dzen.ru/profile/editor](https://dzen.ru/profile/editor) → Статья → заголовок "AI для стоматологии: реальный кейс 12 → 47 заявок..." → Ctrl+V → загрузить 3-5 фото → опубликовать | окно открыто |

Если при паст из буфера получаешь не тот текст — скажи "перезагрузи habr" / "перезагрузи telegram" / "перезагрузи дзен", я переложу.

### Приоритет 3 — после регистрации домена (~1 час DNS пропагации после Reg.ru)

| Где | Что |
|---|---|
| **Vercel** | Импортировать `ai-marketing-natalia` репо → добавить env `ANTHROPIC_API_KEY` → Deploy |
| **Vercel → Settings → Domains** | Добавить natashabrovkina.com → выдадут NS-серверы → переписать в Reg.ru ЛК |
| **Vercel → Settings → Domains** | Добавить nataliyabrovkina.com + natashabrovkina.ru как 301-redirect |

Подробный гайд: [DEPLOYMENT-WALKTHROUGH.md](DEPLOYMENT-WALKTHROUGH.md)

### Приоритет 4 — GitHub repo SEO (5 минут)

Открой https://github.com/nibrovkina-cyber/natalia-marketing-department/settings:
- **Description:** `21 Claude Skills replacing a marketing department for Russian small business · MIT · Schwartz/Ogilvy/Hopkins methodology`
- **Website:** `https://natashabrovkina.com`
- **Topics:** добавь `claude-skills`, `claude-code`, `ai-marketing`, `marketing-automation`, `direct-response`, `russian-marketing`, `ogilvy`, `schwartz`, `hopkins`, `open-source-marketing`, `claude-ai`, `ai-agents`

### Приоритет 5 — push моих локальных коммитов

Когда захочешь — `git push` в `natalia-marketing-department`. У меня 2 коммита на main которые ещё не на GitHub:
- `1922407 growth-system: complete pipeline with 7 articles published to Telegraph`
- `f2cf618 SEO + methodology: README rewrite for GitHub search, Cannell framework, Episode 2`

И коммит изменений в EN README + ночной батч изменений я ещё не закоммитила. Сделаю утром когда сядешь.

### Приоритет 6 — Cannell A/B Test thumbnails

Видео UrU_tapUIxM получило 29 просмотров за сутки = **низкий CTR thumbnail**. 5 минут работы:

1. YouTube Studio → видео → Test & Compare
2. Загрузи 3 варианта thumbnail
3. YouTube тестирует 14 дней автоматически

Подробнее в [methodology/cannell-youtube.md](methodology/cannell-youtube.md).

---

## 📊 Состояние файловой системы

### natalia-marketing-department/
```
README.md                          ✅ обновлён (21 агент, badges, EN-summary, 7 Telegraph-ссылок)
docs/README.en.md                  ✅ NEW — EN-версия для глобальной GitHub-аудитории
growth-system/
├── 8-WEEK-PLAN.md                 ✅
├── DEPLOYMENT-WALKTHROUGH.md      ✅
├── MORNING-BRIEFING.md            ✅ NEW — этот файл
├── PROMPTS-FROM-PLAYBOOK.md       ✅
├── README.md                      ✅
├── SEO-CHECKLIST.md               ✅
├── agents/                        ✅ 6 агентов
├── competitors.md                 ✅
├── icp.md                         ✅
├── inputs/
│   ├── current-keywords.md        ✅
│   ├── published-urls.md          ✅ — 7 Telegraph URLs
│   └── traffic-data.csv           ⏳ — пустая, заполнить через 7 дней
├── methodology/
│   └── cannell-youtube.md         ✅
├── offer.md                       ✅
├── outputs/
│   ├── briefs/                    ✅ 2 брифа
│   ├── distribution-packs/        ✅ 7 базовых + 7 FINAL
│   ├── drafts/                    ✅ 7 drafts по 1500 слов
│   └── keyword-scout-2026-05-03.md ✅
├── scripts/
│   ├── md-to-habr.py              ✅
│   └── publish-telegraph.py       ✅ — переиспользуемый
├── video-series/
│   ├── episode-0-script.md        ✅
│   ├── episode-1-script.md        ✅
│   ├── episode-2-script.md        ✅
│   ├── episode-3-script.md        ✅ NEW
│   ├── episode-4-script.md        ✅ NEW
│   ├── episode-5-script.md        ✅ NEW
│   ├── episode-6-script.md        ✅ NEW
│   ├── episode-7-script.md        ✅ NEW
│   └── video-series-plan.md       ✅
└── voice.md                       ✅
```

### ai-marketing-natalia/
```
app/
├── layout.tsx                    ✅ JSON-LD Person + Organization + SoftwareApplication
├── page.tsx                      ✅ NEW per-page metadata + canonical
├── method/page.tsx               ✅ FAQPage Schema + 5 вопросов
├── tool/layout.tsx               ✅ NEW metadata wrapper
├── gallery/layout.tsx            ✅ NEW metadata wrapper
├── gallery/[slug]/page.tsx       ✅ BreadcrumbList + Article Schema + alt-теги
public/llms.txt                   ✅ NEW для AI-краулеров
```

---

## 🎯 Что было сделано к челленджу "0 → 10K за 8 недель"

**Состояние плейбука Sabrina Ramonov:**
- Step 1: Keyword Scout ✅ (30 ключей, 7 финальных)
- Step 2: Brief + Draft Writers ✅ (7 готовых статей по 1500 слов)
- Step 3: Distribution hooks ✅ (4 платформы × 7 статей = 28 готовых постов)
- Step 4: Multi-platform distribution ⏳ (Telegraph 7/7 ✅, TenChat 1/7, остальные 0/7 — нужна твоя публикация)
- Step 5: Analytics review ⏳ (через 7 дней после первой партии публикаций)

**Чтобы достичь цели нужно:**
- Завтра: опубликовать 3 статьи на 3 платформах (TenChat ✅ уже было, Habr, Дзен)
- На неделе 2: ещё 3 статьи
- На неделе 3: остальные 4
- 2 раза в неделю — TikTok / VK Klipy / YouTube Shorts из видео-нарезок
- Каждое воскресенье — Analytics Reviewer на цифры предыдущей недели

---

## ⚠️ Открытые вопросы / решения требующие тебя

1. **Push в GitHub?** У меня 2 коммита локально + ночной батч. Скажи "пушай" утром.
2. **Telegram канал — bot token есть?** Если да — могу опубликовать пост автономно через Telegram Bot API. Если нет — clipboard ждёт.
3. **Anthropic API ключ — пополнила?** Без этого /tool на natashabrovkina.com выдаёт ошибку посетителям.
4. **Купила домены?** Если да — переходим к Vercel-деплою.

---

## Если хочешь почитать прежде чем что-то делать

1. [SEO-CHECKLIST.md](SEO-CHECKLIST.md) — что в SEO готово, что нет
2. [methodology/cannell-youtube.md](methodology/cannell-youtube.md) — A/B test thumbnails и почему первое видео даёт мало просмотров
3. [DEPLOYMENT-WALKTHROUGH.md](DEPLOYMENT-WALKTHROUGH.md) — после покупки домена

---

## Что я делаю прямо сейчас

Финальный коммит ночных изменений в локальный git. Жду твоего ответа утром.

Доброй ночи 🌙
