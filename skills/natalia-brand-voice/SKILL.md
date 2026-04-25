---
name: natalia-brand-voice
description: Brand voice и tone-of-voice фундамент natalia.com. Определяет КАК пишут все маркетинговые агенты — palette, типографика, voice, что говорим / что НЕ говорим. Используется как контекст для всех остальных natalia-* skills.
version: 1.0.0
---

# natalia · brand voice

**Foundation skill.** Любой natalia-* агент должен прочитать этот файл перед генерацией контента, чтобы output соответствовал бренду.

## Позиционирование

- **Имя:** Natalia Brovkina
- **Компания:** natalia.com — AI Marketing Studio
- **Города:** Москва, Лос-Анджелес
- **Категория:** студия-фрилансер с AI-командой, не агентство и не SaaS
- **Telegram:** [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- **GitHub:** [nibrovkina-cyber](https://github.com/nibrovkina-cyber)

## Tone of Voice

**Редакторский, уверенный, без пафоса, без маркетингового жаргона.**

Нацеливаемся на «журнал Kinfolk», а не «SaaS pricing». Личный голос соло-эксперта, а не корпорация.

### Что мы говорим (примеры)

- «Запусти сама — или передай мне на 30 дней»
- «Удвоила выручку 20 малых бизнесов. Без команды.»
- «Один раз настроила тон — агенты помнят»
- «Без давайте подумаем»
- «Если задача не моя, скажу честно»

### Что мы НЕ говорим

- «Unlock your growth potential with AI»
- «Best-in-class marketing automation»
- «Game-changing / Revolutionary / Cutting-edge»
- «Динамичная команда профессионалов»
- «Качественные услуги под ключ»
- «Мы делаем красиво» (показывай, не рассказывай)
- Любые превосходные степени без числа («лучший», «надёжный»)

## Voice по 4 осям

| Ось | Где мы | Что значит |
|---|---|---|
| Формальный ↔ Разговорный | **Разговорный** (на «ты») | «Запусти сама», не «Запустите сами» |
| Серьёзный ↔ С юмором | **Серьёзный** | Юмор только в контексте, не как приём продаж |
| Экспертный ↔ Дружеский | **Экспертный** + персональный | «Я веду каждый проект сама» |
| Провокационный ↔ Осторожный | **Провокационный** | Прямо называем боль клиента, не виляем |

## Палитра

**ТОЛЬКО** эти цвета. Никаких purple / pink / blue-violet / gradient mesh.

### Warm AI (default — для лендингов и pricing)
| Token | Hex | Назначение |
|---|---|---|
| `--bg` | `#F7F4EE` | Off-white cream фон |
| `--bg-card` | `#FBF9F4` | Светлая карточка |
| `--surface` | `#EFEAE0` | Глубокая cream для секций |
| `--ink` | `#1F1B16` | Near-black warm |
| `--ink-2` | `#4A4339` | Secondary text |
| `--ink-3` | `#8A8175` | Tertiary text / labels |
| `--accent` | `#D9542B` | Rust orange — Primary CTA |

### Navy editorial (для longread и кейсов)
| Token | Hex | Назначение |
|---|---|---|
| `--bg` | `#F4EFE4` | Cream |
| `--ink` | `#0E1B33` | Navy |
| `--accent` | `#B8893A` | Gold leaf |

**Один accent на экран** — primary CTA, link hover, inline emphasis. **Никогда** не в body copy.

## Типографика

Три семейства, в порядке частоты использования:

### 1. Inter (default) — UI, body, headlines
- Headlines: Inter Display 600, letter-spacing −0.025em до −0.035em
- Body: Inter 400, 17/26 (1.55 line-height)
- Display: 96-128px для hero, h1: 64-92px, h2: 40-52px, h3: 24-26px

### 2. Playfair Display Italic 500 — accent words
- **Только отдельные слова** внутри h1/h2 как акцент
- Через CSS class `.italic-display`
- Пример: «Готова <span class="italic-display">удвоить</span> выручку?»
- Никогда не для целого заголовка, никогда не для body

### 3. JetBrains Mono 500 — meta, kickers, prices
- Eyebrow / kicker: 11px, uppercase, letter-spacing 0.14em-0.16em
- Технические метаданные («/ ТАРИФЫ», «v 1.0 · 04.2026»)
- Цены: tabular-nums variant, currency unit smaller

## Spacing

- **Между секциями:** 60-120px (modern AI 2026), не 200px (editorial)
- **Padding страницы:** 48-64px desktop, 24px mobile
- **Padding карточки:** 28-48px
- **Border-radius:** 0 default (sharp), допустимо до 14-22px на специальных карточках
- **Hero price / signature numerals:** 56-92px

## Запреты по визуалу (жёсткие)

- Pill-кнопки с градиентом
- ✓ галочки в feature-листах (используй цифры/точки)
- «Most Popular» badge на тарифе
- Stat-strip «47 млн / 20 / 16» в hero
- Зачёркнутая цена со стрелкой →
- Drop-cap (это для блогов, не лендинга)
- Playfair для целого headline (только italic слова внутри)
- Сравнительная SaaS-таблица с ✓
- Эмодзи в заголовках (📎 ⚡ 🔥 💎)
- Gradient mesh, purple / pink / blue-violet тона
- Card-grid 1:1 для тарифов

## Tone в копирайтинге — формулы

**Hero headline:** `[действие/глагол] + [цифра] + [результат]. [italic дополнение].`
- ✅ «Удвоила выручку 20 малых бизнесов. *Без команды.*»
- ✅ «Растим выручку SMB на 23-58% за 60 дней. *Без давайте подумаем.*»
- ❌ «Качественный маркетинг для бизнеса»

**CTA:** глагол + конкретика
- ✅ «Скачать бесплатно на GitHub →»
- ✅ «Записаться · 3 места →»
- ❌ «Узнать больше», «Связаться с нами»

**Subhead:** механизм или time-bound proof
- ✅ «3 лендинга бесплатно. Без карты. Возврат 14 дней.»
- ❌ «Современные решения для вашего бизнеса»

## Showcase кейсы (используй как примеры)

- **MEDEA Dent** — стоматология на Покровке, заявок ×3.4 за 90 дней
- **Simbios Marketing** — агентство, конверсия в заявку +58% за 60 дней

## Применение в других skills

Когда любой natalia-* skill генерирует контент:

1. Прочитай этот файл первым
2. Проверь tone согласно «Что мы говорим / Что НЕ говорим»
3. Используй только разрешённую палитру
4. Inter для headlines, Playfair italic только на одно слово accent
5. Никаких запретов из списка выше

В финальном блоке `🧠 Почему я так сделал` всегда упоминай Brand voice как один из применённых принципов.
