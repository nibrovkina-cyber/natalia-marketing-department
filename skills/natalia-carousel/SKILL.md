---
name: natalia-carousel
description: Генерирует контент-карусель из 5-10 слайдов для Telegram, VK, LinkedIn, TenChat. Использует natalia-design-system для стиля, natalia-brand-voice для тона. Возвращает HTML-файл со слайдами + инструкцию экспорта в PNG/PDF для публикации.
version: 1.0.0
---

# natalia · carousel design

Превращает один контент-посыл в **карусель из 5-10 слайдов** с единым визуальным языком natalia.com.

## Когда использовать

- Telegram-пост который нужно «вытянуть» в карусель из текста
- Образовательный контент: «5 ошибок копирайтинга», «3 принципа Огилви»
- Анонс кампании / запуска
- Кейс: до → процесс → после → результат
- Свайп-файл инсайтов с бренд-голосом Натальи

## Pre-requisites (читай первыми)

1. **`natalia-brand-voice`** — voice + позиционирование
2. **`natalia-design-system`** — палитра, шрифты, компоненты (warm-AI default)

## Inputs

Спрашиваю в одном сообщении:
1. **Тема / контент-угол** — о чём слайды?
2. **Количество слайдов** — 5 / 7 / 10? (default 7)
3. **Платформа** — Telegram (1080×1080) / VK (1080×1080) / LinkedIn (1080×1350) / TenChat (1080×1350)?
4. **Цель** — обучение / анонс / продажа / brand-awareness?
5. **CTA на последнем слайде** — что делать читателю?
6. **Палитра** — warm (default) или navy?

Если что-то не указано — выдвигаю гипотезы и применяю default.

## Methodology layer

- **OGILVY:** первый слайд = headline. Решает откроют ли карусель. Названная аудитория + конкретный benefit.
- **SCHWARTZ:** определи уровень осведомлённости платформы:
  - Telegram (подписчики уже Solution/Product Aware) → механизм + конкретика
  - Холодный VK → Problem Aware → начинай с боли
  - LinkedIn/TenChat (B2B Product Aware) → кейс с цифрами
- **HOPKINS:** каждый слайд = одна цифра или конкретный факт. Без числа — пролистают.

## Output structure

### Шаблон карусели (7 слайдов default)

| # | Роль | Что на слайде |
|---|---|---|
| 1 | **Hook / cover** | Headline 60-90 знаков + visual accent. Это заголовок газеты — решает откроют или нет. |
| 2 | **Setup / problem** | Проблема, которую решаем. Названная аудитория. Cifрa если есть. |
| 3 | **Insight / контекст** | Почему стандартное решение не работает. |
| 4 | **Frame 1** | Первая часть инсайта / методологии. |
| 5 | **Frame 2** | Вторая часть. |
| 6 | **Frame 3 / proof** | Кейс, цифра, конкретика. |
| 7 | **CTA** | Что делать дальше. Одна команда. Telegram-link или next swipe. |

Для 5-слайдов — урезай 4-5 до одного. Для 10 — добавь больше proof и mini-кейсы.

### HTML-output

Один файл `carousel-<slug>.html` с N разделами `<section class="slide">`. Каждый слайд — full-square (1080×1080) или 4:5 (1080×1350) ratio.

Структура каждого слайда:
- Top: small mono kicker (номер слайда «01 / 07» или категория)
- Middle: главное содержимое (Inter Display headline 48-64px + body 17-22px)
- Bottom: brand mark «natalia.com» или авторская подпись «— Наталья Бровкина»

Код использует `<style>` inline с CSS-переменными из design-system + Google Fonts link.

## Visual rules (из design-system)

- Палитра: warm (default) — `#F7F4EE` фон, `#1F1B16` текст, `#D9542B` accent
- Headline: Inter Display 600, 48-72px, letter-spacing -0.025em
- Italic accent: одно слово через `.italic-display` (Playfair italic 500) на 1-2 слайдах максимум
- Body: Inter 400, 17-22px, line-height 1.5
- Mono kicker: JetBrains Mono 500, 11px, uppercase, letter-spacing 0.14em
- Sharp corners (radius 0)
- Один accent на слайд — orange ровно в одном месте: либо номер, либо underline под key word, либо CTA-кнопка
- **Никаких** градиентов, эмодзи в headline, drop-cap, pill-кнопок

## Export instruction

В конце вывода указываешь как превратить HTML в PNG для публикации:

```bash
# Установить puppeteer (если ещё нет)
npm install -g puppeteer

# Запустить export-script (вместе с outputом сгенерирую если попросят)
node carousel-export.mjs carousel-<slug>.html
```

Альтернатива для не-разработчиков:
1. Открыть HTML в Chrome
2. Каждый слайд: правый клик → Inspect → выбрать `<section class="slide">` → правый клик → Capture node screenshot
3. Сохранить как PNG

## Workflow

1. **Read** brand-voice + design-system skills
2. **Ask** inputs выше (одним сообщением)
3. **Plan** — пропиши план содержимого 7 слайдов прежде чем писать HTML
4. **Generate** HTML файл с N слайдов
5. **Output** — путь к файлу + текстовый план каждого слайда + export instruction
6. **Suggest** — какие skills логично применить дальше:
   - `natalia-atomizer` — переработать карусель в текст-пост, story для других платформ
   - `natalia-social` — спланировать публикацию в контент-плане
   - `natalia-ads` — превратить hook-слайд в рекламный креатив

## Required closing format

```
---
**🧠 Почему я так сделал:**

- **Brand voice** — [применил голос Натальи: что сказал/не сказал]
- **Design system** — [warm/navy палитра, какой accent, italic accent на каком слове]
- **Ogilvy** — [какой hook на cover-слайде, какая formula]
- **Schwartz** — [уровень осознанности под платформу]
- **Hopkins** — [какие конкретные цифры/факты в слайдах]
- **Чего я НЕ делал** — [один типичный приём типа эмодзи-заголовка / drop-cap]
```

## Examples

### Carousel «Почему 95% лендингов не продают» (7 слайдов, образовательный)

1. **Cover:** «95% лендингов не продают. Я разобрала <em>сотни</em>. Вот что я заметила.»
2. **Problem:** «Дизайнер делает красиво. Маркетолог пишет красиво. Но клиенты не звонят.»
3. **Insight:** «Проблема не в красоте. В уровне осознанности.»
4. **Frame 1 (Schwartz):** «5 уровней — от Unaware до Most Aware. Каждый требует свой headline.»
5. **Frame 2 (Ogilvy):** «Заголовок = 80% бюджета. Если он не работает — остальное не прочитают.»
6. **Frame 3 (proof):** «Стоматология MEDEA: переписали hero под Problem Aware. Заявок ×3.4 за 90 дней.»
7. **CTA:** «Полный разбор методологии — natalia.com/method. Бесплатно.»
