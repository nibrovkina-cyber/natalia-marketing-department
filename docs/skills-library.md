# natalia · skills library

Каталог всех 21 skills из репо `natalia-marketing-department` v1.1.0.

**Импорт в Notion:**
1. Создай новую страницу в Notion (`+ New page`)
2. `…` → `Import` → `Markdown & CSV`
3. Выбери этот файл (`docs/skills-library.md`)
4. Notion распарсит таблицу ниже как **inline database**
5. После импорта добавь свойство `Source URL` со ссылками на GitHub (опционально)

**Auto-sync (когда подключим Notion MCP):**
Routine `npm run sync-notion-library` будет проверять изменения в `skills/` и обновлять Notion-базу раз в неделю.

---

## Skills

| Name | Category | Description | Version | Path |
|---|---|---|---|---|
| natalia | Orchestrator | Маркетинговый отдел из 21 AI-агента + campaign-manager оркестратор для русского SMB. Вызывает foundation → function → specialty. | 1.1.0 | skills/natalia/SKILL.md |
| natalia-brand-voice | Foundation | Voice, позиционирование, tone-of-voice фундамент natashabrovkina.com. Палитра, типографика, что говорим / что НЕ говорим. Используется как контекст всеми остальными skills. | 1.0.0 | skills/natalia-brand-voice/SKILL.md |
| natalia-design-system | Foundation | Дизайн-система: токены палитры (warm-AI default + navy alt), типографика (Inter Display + Playfair italic + JetBrains Mono), компоненты, motion-правила. | 1.0.0 | skills/natalia-design-system/SKILL.md |
| natalia-positioning | Function | Стратегия позиционирования. Находит угол, который отличает продукт. 8 фреймворков по Огилви/Шварцу/Хопкинсу. | 1.0.0 | skills/natalia-positioning/SKILL.md |
| natalia-copy | Function | Прямой отклик копирайтинг. Тексты по Schwartz (5 уровней осведомлённости), Hopkins (Scientific Advertising), Ogilvy (заголовок 80%). | 1.0.0 | skills/natalia-copy/SKILL.md |
| natalia-leadmagnet | Function | Оффер который скачивают. Двухрежимный: стратегия (3 идеи) или сборка (готовый документ). По Hopkins/Schwartz/Ogilvy. | 1.0.0 | skills/natalia-leadmagnet/SKILL.md |
| natalia-landing | Function | CRO-аудит и переписка посадочной страницы. 7 зон. Первые 5 секунд решают всё. | 1.0.0 | skills/natalia-landing/SKILL.md |
| natalia-email | Function | Welcome / nurture / запуск email-серии. Schwartz-карта (1 письмо = 1 уровень осведомлённости). | 1.0.0 | skills/natalia-email/SKILL.md |
| natalia-atomizer | Function | 1 пост → 15 форматов под Telegram, VK, LinkedIn, TenChat, Email, Shorts/Reels. Адаптация под уровень платформы. | 1.0.0 | skills/natalia-atomizer/SKILL.md |
| natalia-social | Function | SMM-стратег для Telegram + ВКонтакте. Контент-план 30 дней + маркировка рекламы (ОРД, ERID). | 1.0.0 | skills/natalia-social/SKILL.md |
| natalia-ads | Function | VK Ads + Яндекс.Директ креативы. Хороший CTR от 0.8% / 5%. По Hopkins/Schwartz. | 1.0.0 | skills/natalia-ads/SKILL.md |
| natalia-seo | Function | SEO + GEO (AI-search). Яндекс vs Google vs ChatGPT/Perplexity/Gemini. E-E-A-T для Google, поведенческие для Яндекса. | 1.0.0 | skills/natalia-seo/SKILL.md |
| natalia-competitors | Function | Аналитика конкурентов. 7 пунктов разведки. Слабые места = твоя возможность для дифференциации. | 1.0.0 | skills/natalia-competitors/SKILL.md |
| natalia-funnel | Function | Воронка продаж для SMB. CJM, точки потери, Schwartz по этапам. Среднее теряется 68% между заявкой и оплатой. | 1.0.0 | skills/natalia-funnel/SKILL.md |
| natalia-launch | Function | Плейбук запуска: предзапуск → запуск → пост-запуск. Schwartz-провод аудитории через 5 уровней. | 1.0.0 | skills/natalia-launch/SKILL.md |
| natalia-brand | Function | Tone of voice + личный бренд для LinkedIn / TenChat. 4 оси голоса. Формула поста: хук + история + вывод + вопрос. | 1.0.0 | skills/natalia-brand/SKILL.md |
| natalia-newsletter | Function | Контентная рассылка. 9 форматов (curated, story, big-idea, case, framework, contra, bts, Q&A, roundup). | 1.0.0 | skills/natalia-newsletter/SKILL.md |
| natalia-webdesign | Function | Полный HTML-лендинг за 60 секунд из URL/брифа. Premium-дизайн с CSS-анимациями. | 1.0.0 | skills/natalia-webdesign/SKILL.md |
| natalia-proposal | Function | Коммерческое предложение для B2B. 7-блочная структура от боли клиента до next step. | 1.0.0 | skills/natalia-proposal/SKILL.md |
| natalia-campaign-planner | Specialty | Полный campaign-brief с research, positioning, ICP, KPI, channel-mix, funnel mapping, budget allocation, accountability. | 1.0.0 | skills/natalia-campaign-planner/SKILL.md |
| natalia-carousel | Specialty | 5-10 слайдов карусели для Telegram/VK/LinkedIn. HTML на бренде. Export → PNG/PDF. | 1.0.0 | skills/natalia-carousel/SKILL.md |
| natalia-motion | Specialty | 30-60 секунд HTML-видео (CSS keyframes + SVG). Storyboard-first workflow. Export → MP4. | 1.0.0 | skills/natalia-motion/SKILL.md |

---

## Категории

- **Orchestrator** (1) — главный диспетчер. Вызывает foundation → function → specialty в правильном порядке.
- **Foundation** (2) — `brand-voice` + `design-system`. Любой function/specialty skill читает их первыми.
- **Function** (16) — повседневные маркетинговые задачи. Каждый автономный.
- **Specialty** (3) — сложные деливераблы которые комбинируют несколько function skills (planning + visual + production).

## Workflow

1. **Точечная задача** — вызывай function skill напрямую (`/natalia-landing`, `/natalia-ads`)
2. **Полная кампания** — вызывай orchestrator (`Запусти кампанию: онлайн-курс по B2B-продажам, 200k₽, 60 дней`)
3. **Визуальный артефакт** — вызывай specialty (`/natalia-carousel`, `/natalia-motion`)

## Methodology layer (применяется во всех skills)

- **Ogilvy** — верифицируемые утверждения, named-audience, sell-the-effect
- **Schwartz** — 5 уровней осведомлённости (Unaware → Most Aware)
- **Hopkins** — Scientific Advertising, цифры вместо прилагательных

## Russian-market context

- Каналы: Яндекс.Директ, VK Ads, Telegram, ВКонтакте, Авито, TenChat
- Платежи: ЮKassa, СБП, Тинькофф Бизнес
- Аналитика: Яндекс.Метрика, Roistat, Calltouch
- Маркетплейсы: Wildberries, Ozon, Яндекс.Маркет
- Закон: ОРД-маркировка ERID, медреклама с дисклеймером

## Showcase кейсы

Используются как примеры во всех skills:
- **MEDEA Dent** (стоматология, Покровка) — заявок ×3.4 за 90 дней
- **Simbios Marketing** (агентство, Москва) — конверсия в заявку +58% за 60 дней

## Author

**Наталья Бровкина** · [natashabrovkina.com](https://natashabrovkina.com) · [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)

## License

MIT — open source. Форкай, адаптируй, делись.

GitHub: <https://github.com/nibrovkina-cyber/natalia-marketing-department>
