# natalia-marketing-department · AI-маркетинговый отдел из 21 агента в Claude Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Skills](https://img.shields.io/badge/Claude-Skills-orange)](https://docs.claude.com/en/docs/claude-code/skills)
[![Made for SMB](https://img.shields.io/badge/SMB-Russia-blue)](https://natashabrovkina.com)

**Бесплатный AI-маркетинговый отдел из 21 агента** для малого и среднего бизнеса в России. Open source. MIT лицензия. Работает на Claude Code с методологией Ogilvy / Schwartz / Hopkins.

🇬🇧 **English:** 21 open-source Claude Skills replacing a marketing department for Russian small business. Schwartz/Ogilvy/Hopkins direct response methodology baked in. Free, MIT, runs on Claude Code with Anthropic API ($5-30/month).

Скачивай → копируй в `~/.claude/skills/` → запускай в Claude Code. Никакого аккаунта, никакой подписки. Работает локально с твоим Anthropic API ключом.

**Кейсы:** стоматология выросла с 12 до 47 заявок в неделю за 6 недель. Греческое кафе перевело контент-план на 1 человека вместо 3.

> **Часть проекта [natashabrovkina.com](https://natashabrovkina.com)** — AI Marketing Studio Натальи Бровкиной. Это бесплатная версия. Hosted-версия с UI запускается летом 2026 — записаться в waitlist на [natashabrovkina.com/waitlist](https://natashabrovkina.com/waitlist).

---

## Что внутри

21 узкий агент на методологии **Ogilvy / Schwartz / Hopkins**:

| # | Команда | Что делает |
|---|---|---|
| 01 | `/natalia-positioning` | Найди угол который делает тебя другим |
| 02 | `/natalia-copy` | Direct response: тексты по Schwartz, Hopkins, Ogilvy |
| 03 | `/natalia-leadmagnet` | Лид-магнит: оффер который скачивают + полная сборка |
| 04 | `/natalia-landing` | Аудит и переписка посадочной страницы |
| 05 | `/natalia-email` | Welcome / nurture / запуск — серии которые читают |
| 06 | `/natalia-atomizer` | 1 пост → 15 форматов для всех платформ |
| 07 | `/natalia-social` | Telegram / VK контент-план + маркировка рекламы |
| 08 | `/natalia-ads` | VK Ads + Яндекс.Директ — тексты, аудитории, CPL |
| 09 | `/natalia-seo` | Яндекс / Google / GEO для AI-поиска |
| 10 | `/natalia-competitors` | Разведка по 7 пунктам |
| 11 | `/natalia-funnel` | CJM, точки потери, как поднять конверсию |
| 12 | `/natalia-launch` | Плейбук запуска: предзапуск → запуск → рост |
| 13 | `/natalia-brand` | Tone of voice, личный бренд для LinkedIn / TenChat |
| 14 | `/natalia-newsletter` | Контентная рассылка которую ждут |
| 15 | `/natalia-webdesign` | Опиши бизнес — получи готовый HTML-лендинг |
| 16 | `/natalia-proposal` | КП которое читают и на которое соглашаются |
| 17 | `/natalia-brand-voice` | Voice/tone-фундамент — как пишут все агенты |
| 18 | `/natalia-design-system` | Дизайн-токены и компоненты для HTML/CSS-выходов |
| 19 | `/natalia-campaign-planner` | Полная кампания из брифа: positioning → KPI → calendar |
| 20 | `/natalia-carousel` | Карусель из 5–10 слайдов для Telegram / VK / TenChat |
| 21 | `/natalia-motion` | HTML-видео (CSS keyframes + SVG) для лендинга / соцсетей |

Плюс мастер-skill `natalia` — оркестратор который знает обо всех 21.

---

## Установка (5 минут)

### Требования
- [Claude Code](https://claude.com/claude-code) (бесплатно)
- Anthropic API ключ (можно оформить на [console.anthropic.com](https://console.anthropic.com))

### Шаг 1 — клонировать репо

```bash
git clone https://github.com/nibrovkina-cyber/natalia-marketing-department.git
cd natalia-marketing-department
```

### Шаг 2 — установить skills

**macOS / Linux:**
```bash
mkdir -p ~/.claude/skills
cp -r skills/* ~/.claude/skills/
```

**Windows (Git Bash или WSL):**
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

### Шаг 3 — запустить в Claude Code

Открой любую папку проекта в Claude Code. Напиши:

```
/natalia-landing https://medeadent.tilda.ws
```

Или:

```
Используй natalia-positioning skill. Я открываю стоматологию в Москве,
средний чек 18 000 ₽, конкуренты — две клиники в радиусе километра.
```

---

## Методология

Каждый агент работает по трём проверенным десятилетиями принципам:

### Ogilvy — *заголовок решает 80%*
Любое утверждение о продукте должно быть **верифицируемым**. Прилагательные «качественный», «лучший», «профессиональный» — запрещены. Заменяются на цифру, сравнение или цитату.

### Schwartz — *5 уровней осведомлённости*
До любого ответа агент мысленно определяет на каком уровне аудитория:
1. **Unaware** — не знают о проблеме
2. **Problem Aware** — знают боль, не знают решения
3. **Solution Aware** — знают что решения есть
4. **Product Aware** — знают о тебе, не купили
5. **Most Aware** — готовы купить

Письмо «не своего» уровня = отписка. Лендинг «не своего» уровня = пустая корзина.

### Hopkins — *Scientific Advertising*
Реклама = продавец в печати. Продавец не говорит «мы команда профессионалов», он говорит «из 847 клиентов 92% вернулись».

---

## Российский рынок

Агенты адаптированы под:

- **Каналы трафика:** Яндекс.Директ, VK Ads, Telegram Ads, Telegram-каналы, ВКонтакте, Авито, TenChat
- **Платёжные системы:** ЮKassa, СБП, Тинькофф Бизнес, Робокасса
- **Аналитика:** Яндекс.Метрика, Roistat, Calltouch
- **Маркетплейсы:** Wildberries, Ozon, Яндекс.Маркет
- **Закон РФ:** маркировка рекламы через ОРД (токен ERID), закон о рекламе медицинских услуг (предупреждение о противопоказаниях)
- **Типовые отрасли:** стоматологии, салоны красоты, рестораны, EdTech, фитнес, B2B-услуги, локальные магазины

---

## Showcase

Реальные кейсы из портфолио Натальи которые показаны в [YouTube-демо](https://www.youtube.com/watch?v=UrU_tapUIxM):

| Кейс | Метрика | Что сделали |
|---|---|---|
| **MEDEA Dent** · стоматология, Покровка, Москва | заявок **×3.4** за 90 дней | Hero с врачами вместо stock-отзывов, прозрачные цены, FAQ закрывающий 6 возражений |
| **Simbios Marketing** · агентство, Москва | конверсия в заявку **+58%** за 60 дней | Killer-headline «13 500 водителей таксопаркам за 1 800 ₽ за лида» вместо абстракций |

---

## Tier-ы продукта natashabrovkina.com

Эта open-source версия — **первый из трёх** уровней:

| Tier | Что | Цена |
|---|---|---|
| 🆓 **Бесплатно** (этот репо) | 21 skill локально, свой API ключ | 0 ₽ |
| 💼 **Инструмент** ([getjuniors.pro](https://getjuniors.pro/)) | Hosted-версия: AI-сотрудники внутри ваших инструментов | 2 990 ₽ / мес |
| 🤝 **Со мной** ([Telegram](https://t.me/nataliyabrovkina)) | Я лично делаю под ключ за 30 дней | 49 000 ₽ |

---

## Contributing

Pull request-ы приветствуются. Особенно:
- Новые showcase-кейсы (с твоего реального бизнеса, с цифрами)
- Адаптации под другие рынки (Беларусь, Казахстан)
- Перевод на английский для EN-аудитории
- Дополнительные business types в `BUSINESS_TYPES`

Issues тоже — если нашёл баг или хочешь обсудить новый агент.

---

## Статьи и видео

Подробные разборы каждого из 21 агентов и методологии — на [Telegraph](https://telegra.ph/):

- [Claude для маркетинга: 21 готовый агент вместо одного маркетолога](https://telegra.ph/Claude-dlya-marketinga-21-gotovyj-agent-vmesto-odnogo-marketologa-05-03)
- [Claude Skills: что это и почему они убивают рынок промпт-каналов](https://telegra.ph/Claude-Skills-chto-ehto-i-pochemu-oni-ubivayut-rynok-prompt-kanalov-na-Patreon-05-03)
- [Как сделать маркетинг без маркетолога: пошаговая система](https://telegra.ph/Kak-sdelat-marketing-bez-marketologa-21-AI-agent-v-Claude-vmesto-otdela-za-100Kmes-05-03)
- [AI для стоматологии: реальный кейс 12 → 47 заявок за 6 недель](https://telegra.ph/AI-dlya-stomatologii-realnyj-kejs-12--47-zayavok-za-6-nedel-bez-agentstva-05-03)
- [Уровни осознанности по Швартцу: 5 уровней которые меняют всё](https://telegra.ph/Urovni-osoznannosti-po-SHvartcu-5-urovnej-kotorye-menyayut-vsyo-v-kopirajtinge-05-03)
- [Email-рассылка с AI: welcome-серия из 5 писем за 30 минут](https://telegra.ph/Email-rassylka-s-AI-welcome-seriya-iz-5-pisem-za-30-minut-05-03)
- [Claude Code на Windows: 3 способа установки за 10 минут](https://telegra.ph/Claude-Code-na-Windows-3-sposoba-ustanovki-za-10-minut-05-03)

**Видео-разбор системы:** [youtube.com/watch?v=UrU_tapUIxM](https://www.youtube.com/watch?v=UrU_tapUIxM)

---

## Author

**Наталия Бровкина** (Nataliya Brovkina) · AI Marketing Studio
- 🌐 Сайт: [natashabrovkina.com](https://www.natashabrovkina.com/) · Продукт: [getjuniors.pro](https://getjuniors.pro/)
- 💬 Telegram: [t.me/nataliyabrovkina](https://t.me/nataliyabrovkina)
- 🎥 YouTube: [@NateBrovk](https://www.youtube.com/@NateBrovk) (RU) · [@nataliyabrovkina](https://www.youtube.com/@nataliyabrovkina) (EN)
- 💼 LinkedIn: [nataliya-brovkina](https://www.linkedin.com/in/nataliya-brovkina-b42a3bb6/)
- 🐦 X: [@NataliyaBrovk](https://x.com/NataliyaBrovk)

## License

[MIT](LICENSE) — форкай, адаптируй под свой бренд, делись изменениями обратно. При использовании в коммерческих продуктах оставь упоминание «Powered by natashabrovkina.com» или ссылку на этот репо.

---

## Almost done?

Если у тебя получилось установить и запустить — **дай ⭐ репозиторию.** Это помогает другим предпринимателям его найти.

Если что-то не запустилось — открой [issue](https://github.com/nibrovkina-cyber/natalia-marketing-department/issues), я отвечаю в течение дня.
