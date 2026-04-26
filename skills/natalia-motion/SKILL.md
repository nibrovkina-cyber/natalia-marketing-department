---
name: natalia-motion
description: Генерирует 30-60 секундное HTML-видео (CSS keyframes + SVG анимация) для лендинга, hero-секции или социальной сети. Использует natalia-design-system. Возвращает один HTML-файл готовый к встраиванию в сайт или экспорту в MP4.
version: 1.0.0
---

# natalia · animated motion

Создаёт **HTML-анимацию 30-60 секунд** в брендовом стиле для использования:
- В hero-секции лендинга как explainer
- На YouTube как story-визуал
- В рекламном креативе VK Ads (через export → MP4)
- В Telegram-канале (loop GIF)

## Когда использовать

- Хочешь explainer-видео для нового продукта без съёмок
- Нужна анимация для презентации питча
- Lead-magnet «нативное видео» для рассылки
- Hero-loop на лендинге чтобы передать ощущение продукта

## Pre-requisites

1. **`natalia-brand-voice`** — voice + позиционирование
2. **`natalia-design-system`** — палитра, шрифты, motion-правила

## Inputs

Спрашиваю в одном сообщении:
1. **Тема / story** — что показываем? (запуск продукта / explainer / testimonial / showcase)
2. **Длительность** — 15s / 30s / 60s? (default 30s)
3. **Где будет крутиться** — hero лендинга / YouTube / VK Ads / Telegram?
4. **Format** — landscape (16:9 1920×1080) / square (1:1 1080×1080) / vertical (9:16 1080×1920)?
5. **Основной message** — одна-две фразы которые должны зацепиться в памяти
6. **CTA в конце** — куда направляем зрителя?

## Methodology layer

- **OGILVY:** первые 3 секунды = hook. Visual + headline в первом кадре. Без хука дальше не смотрят.
- **SCHWARTZ:** для соц-сети уровень 1-2 (Unaware/Problem) → начинай с боли или провокации. Для лендинга-сайта уровень 3-4 (Solution/Product) → сразу механизм/преимущество.
- **HOPKINS:** хотя бы одна цифра в видео. «Удвоила выручку 20 бизнесов» — попадает в память лучше чем «помогаю предпринимателям».

## Storyboard (mandatory)

**Никогда не генерируешь видео без storyboard.** Сначала набрасываешь план кадров в текст:

```
00:00–00:03  Hook: «Удвоила выручку 20 бизнесов» (Inter Display 96px, fade-in)
00:03–00:08  Problem: «Тратишь часы на копирайт?» (Playfair italic accent на «часы»)
00:08–00:14  Solution: 16 точек-агентов появляются последовательно (gold dots, pulse)
00:14–00:22  Process: 3 шага — бриф → AI работает → готовый лендинг (split screens)
00:22–00:28  Proof: «MEDEA Dent: ×3.4 заявок за 90 дней» (number counter animation)
00:28–00:30  CTA: «natashabrovkina.com/tool — попробовать бесплатно» (call-to-action button slide-in)
```

Каждый кадр имеет:
- Время начала и окончания
- Главный визуал (typography / shape / icon)
- Анимация (fade / slide / scale / counter)
- Sound mood (подразумеваемый — для будущего озвучивания)

## Visual approach

Используй **только**:
- CSS animations (keyframes, transitions)
- SVG для шейпов и линий
- Inter / Playfair Italic / JetBrains Mono — шрифты
- Палитра warm (default) или navy

**Никакого** WebGL, three.js, Lottie. Простая HTML/CSS/SVG анимация — она экспортируется в MP4 через puppeteer + ffmpeg.

### Стандартные motion-приёмы

| Приём | Когда | CSS |
|---|---|---|
| **Type fade-in** | Headline появляется | `opacity: 0 → 1, translateY(20px → 0), 800ms ease-out` |
| **Counter** | Цифра считается вверх | `@keyframes count + JS for incremental update` |
| **Dot pulse** | 16 агентов | `scale 1 → 1.15 → 1, opacity 0.3 → 0.85, 2.6s infinite` |
| **Underline draw** | Подчеркнуть слово | `width: 0 → 100%, 600ms ease` |
| **Scale-reveal** | Logo / brand mark | `transform scale(0.9 → 1), opacity 0 → 1, 1s` |
| **Marquee** | Бегущая строка социальных доказательств | `translateX 0 → -100%, 20s linear infinite` |
| **Slide stack** | Сценарий "до/после" | `transform translateX, 600ms ease` |

### Что НЕЛЬЗЯ

- ❌ Сложный 3D и parallax
- ❌ Stock-видео фоном
- ❌ Skeuomorphic тени и эффекты
- ❌ Цветные градиенты типа purple/blue (нарушение бренда)
- ❌ Эмодзи в кадрах
- ❌ Типография в Comic Sans или подобных шрифтах

## HTML structure

```html
<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8">
  <title>natalia · motion · [campaign-name]</title>
  <style>
    /* Brand tokens */
    :root {
      --bg: #F7F4EE;
      --ink: #1F1B16;
      --accent: #D9542B;
      --accent-soft: rgba(217, 84, 43, 0.08);
    }
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Playfair+Display:ital,wght@1,500&family=JetBrains+Mono:wght@500&display=swap');
    body { background: var(--bg); color: var(--ink); margin: 0; }
    .stage {
      width: 100vw; height: 100vh;
      position: relative; overflow: hidden;
    }
    .scene { position: absolute; inset: 0; opacity: 0; }
    .scene.active { opacity: 1; }
    /* keyframes для каждой сцены */
  </style>
</head>
<body>
  <div class="stage">
    <div class="scene scene-1">...</div>
    <div class="scene scene-2">...</div>
    <!-- ... -->
  </div>
  <script>
    // Простая state-machine: переключаем .active класс по setTimeout согласно storyboard
  </script>
</body>
</html>
```

## Workflow

1. **Read** brand-voice + design-system skills
2. **Ask** inputs (один раз, все 6 вопросов)
3. **Storyboard FIRST** — текстовый план кадров с таймингами. Подтвердить у пользователя.
4. **Generate** HTML файл целиком (один файл, всё inline)
5. **Output** — путь к файлу + storyboard + инструкция как открыть и записать в MP4
6. **Suggest next** — какие skills полезны:
   - `natalia-landing` — встроить в hero
   - `natalia-ads` — адаптировать под VK Ads креатив
   - `natalia-social` — добавить в контент-план как Reels/Shorts

## Export to MP4 (опционально, если просят)

```bash
# Установить ffmpeg + puppeteer
npm install puppeteer

# Запустить export-script
node motion-export.mjs motion-<slug>.html --duration 30 --output motion-<slug>.mp4
```

Под капотом — puppeteer скриншотит каждые 50ms (20fps), ffmpeg склеивает в MP4.

## Required closing format

```
---
**🧠 Почему я так сделал:**

- **Brand voice** — [применил позиционирование, какие фразы Натальи использовал]
- **Design system** — [палитра, шрифты, motion-приёмы]
- **Ogilvy** — [hook в первые 3 секунды, какой сильный визуал]
- **Schwartz** — [уровень аудитории и где видео будет крутиться]
- **Hopkins** — [какая цифра / факт в видео]
- **Чего я НЕ делал** — [parallax / stock-video / другие шаблонные приёмы]
```

## Examples

### 30-секундный hero-explainer для natashabrovkina.com

```
00:00–00:03  «Удвоила выручку 20 бизнесов.» (Inter 96px, fade + 0.5s pause)
00:03–00:06  «Без команды.» (Playfair italic 96px steel-color, slide-in)
00:06–00:12  16 dots появляются grid 8×2, каждая pulse, gold accent
00:12–00:18  Под каждой dot текст-роль появляется: «копирайт» «SEO» «дизайн»...
00:18–00:24  «Методология Огилви/Шварца/Хопкинса» mono-line under
00:24–00:28  «MEDEA Dent · ×3.4 заявок за 90 дней» (counter from 1 to 3.4)
00:28–00:30  «natashabrovkina.com/tool — попробовать бесплатно» (CTA pill)
```
