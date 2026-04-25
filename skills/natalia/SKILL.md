---
name: natalia
description: Маркетинговый отдел из 21 AI-агента + campaign-manager оркестратор для русского SMB. Методология Ogilvy/Schwartz/Hopkins. Адаптировано под РФ-каналы (Яндекс.Директ, VK, Telegram, ЮKassa). Часть проекта natalia.com от Натальи Бровкиной. Open source MIT.
version: 1.1.0
---

# natalia · marketing department · campaign manager

**21 AI-агент** + оркестратор для маркетинга малого и среднего бизнеса в России. Методология **Ogilvy / Schwartz / Hopkins** на базе всех агентов.

Работает как **campaign-manager**: получаешь короткий бриф → оркестратор сам вызывает нужные skills → собирает full deliverable.

## Архитектура

### Foundation skills (читаются всегда первыми)

| Skill | Что задаёт |
|---|---|
| `natalia-brand-voice` | Voice, позиционирование, tone, что говорим/не говорим |
| `natalia-design-system` | Палитра, шрифты, компоненты для всех визуальных артефактов |

### Function skills (повседневные задачи)

| Команда | Агент | Когда вызывать |
|---|---|---|
| `/natalia-positioning` | Позиционирование | Начало любой кампании, новый продукт |
| `/natalia-copy` | Прямой отклик | Лендинг, реклама, email — основной копирайтинг |
| `/natalia-leadmagnet` | Лид-магнит | Free-tier контент для входа в воронку |
| `/natalia-landing` | Лендинг / CRO | Аудит + переписка посадочной |
| `/natalia-email` | Email-серии | Welcome, nurture, запуск |
| `/natalia-atomizer` | Атомайзер | 1 пост → 15 форматов |
| `/natalia-social` | Telegram / VK | Контент-план 30 дней |
| `/natalia-ads` | Реклама | VK Ads, Яндекс.Директ креативы |
| `/natalia-seo` | SEO / Яндекс / GEO | Позиции в поиске + AI-search |
| `/natalia-competitors` | Конкуренты | Разведка, дифференциация |
| `/natalia-funnel` | Воронка продаж | CJM, точки потери |
| `/natalia-launch` | Запуск продукта | Плейбук предзапуск → запуск |
| `/natalia-brand` | Бренд и голос | Tone of voice, личный бренд |
| `/natalia-newsletter` | Рассылка | Контентная рассылка |
| `/natalia-webdesign` | Дизайн сайта | Полный HTML-лендинг |
| `/natalia-proposal` | Предложение клиенту | КП для B2B |

### Specialty skills (визуальные артефакты)

| Команда | Агент | Когда вызывать |
|---|---|---|
| `/natalia-campaign-planner` | Campaign brief | Запуск новой кампании от 0 до плана |
| `/natalia-carousel` | Carousel design | Визуальный пост 5-10 слайдов |
| `/natalia-motion` | Animated motion | HTML-видео 30-60 сек |

## Как работает campaign-manager

Когда пользователь пишет:
> «Запускаю новый онлайн-курс по B2B-продажам, бюджет 200k₽, 60 дней до старта»

Оркестратор:

### Шаг 1 — Foundation
Читает `natalia-brand-voice` + `natalia-design-system` как контекст.

### Шаг 2 — Strategic planning
Вызывает `natalia-campaign-planner` который:
- Спрашивает 8 уточняющих inputs (продукт, ICP, KPI, etc.)
- Делает research (через WebSearch если есть)
- Выдаёт `CAMPAIGN-BRIEF.md` с positioning, channel-mix, funnel, budget

### Шаг 3 — Если нужно — глубже в позиционирование
Если в брифе positioning слабый или нет конкурентного контекста:
- `natalia-competitors` для разведки
- `natalia-positioning` для угла

### Шаг 4 — Production assets
Параллельно (или последовательно по приоритету):
- `natalia-landing` или `natalia-webdesign` — лендинг кампании
- `natalia-copy` — hero + CTA + body
- `natalia-email` — welcome + nurture + запуск
- `natalia-ads` — креативы для VK / Директ
- `natalia-social` — контент-план Telegram + VK
- `natalia-leadmagnet` — opt-in оффер для верха воронки

### Шаг 5 — Visual layer
- `natalia-carousel` — образовательные посты для соцсетей
- `natalia-motion` — hero-видео для лендинга
- `natalia-newsletter` — еженедельный апдейт-выпуск

### Шаг 6 — Output

Создаёт папку `campaigns/<slug>/` с:
- `CAMPAIGN-BRIEF.md` — стратегический документ
- `landing.html` — готовый лендинг
- `emails/` — серия писем
- `ads/` — креативы под каждый канал
- `social-calendar.md` — контент-план на 30-60 дней
- `carousels/` — визуальные посты
- `motion.html` — explainer-видео
- `tracker.md` — KPI, что мерим, где смотрим

## Workflow для пользователя

### Минимальный путь
```
/natalia-campaign-planner
```
Получаешь только стратегию и план. Дальше сам решаешь какие production-skills включить.

### Полный путь — orchestration
```
Запусти полную кампанию: онлайн-курс по B2B-продажам, бюджет 200k₽, 60 дней.
```
Оркестратор сам спрашивает уточнения и вызывает все нужные skills последовательно.

### Ad-hoc — точечная задача
```
/natalia-landing https://мой-сайт.ru
/natalia-carousel  тема: «5 ошибок копирайтинга»
/natalia-ads  для онлайн-курса B2B-продаж
```
Каждый skill работает автономно если не нужна полная кампания.

## Methodology (применяй неявно во всех skills)

- **OGILVY** — заголовки и позиционирование. Любое утверждение о продукте — верифицируемое (число + named-audience + срок). Никаких «качественный/лучший/профессиональный».
- **SCHWARTZ** — определи уровень осведомлённости (1-5) до того как писать. Один контент не работает на всех уровнях.
- **HOPKINS** — реклама = продавец в печати. Конкретные цифры, факты, кейсы. «92% вернулись из 847» > «большинство довольны».

## Russian-market context (везде применяется)

- **Каналы:** Яндекс.Директ, VK Ads, Telegram, Telegram Ads, ВКонтакте, Авито, TenChat, LinkedIn (через VPN)
- **Платежи:** ЮKassa, СБП, Тинькофф Бизнес, Робокасса
- **Аналитика:** Яндекс.Метрика, Roistat, Calltouch
- **Маркетплейсы (отдельно):** Wildberries, Ozon, Яндекс.Маркет
- **Закон РФ:** маркировка рекламы (ОРД, токен ERID), закон о рекламе медуслуг
- **Типовые отрасли:** стоматологии, салоны красоты, рестораны, EdTech, фитнес, B2B-услуги

## Showcase

Готовые разборы в YouTube-демо:
- **MEDEA Dent** — стоматология на Покровке, заявок ×3.4 за 90 дней
- **Simbios Marketing** — агентство, конверсия в заявку +58% за 60 дней

## Skill versioning

Каждый sub-skill имеет `version: x.y.z` в frontmatter. При обновлении skill — увеличиваем minor (x.Y.z) если backwards-compatible изменение, major (X.y.z) если ломающие.

Когда подключаешь skill через `cp -r`, проверь версию в `SKILL.md` — должна быть свежее предыдущей.

## Author & License

**Наталья Бровкина**
- Сайт: [natalia.com](https://natalia.com)
- Telegram: [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- GitHub: [nibrovkina-cyber/natalia-marketing-department](https://github.com/nibrovkina-cyber/natalia-marketing-department)

MIT — форкай, адаптируй, делись изменениями обратно.
