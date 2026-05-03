# 3 промпта из плейбука "0 → 10K"

Точно как в исходной статье. Адаптировано под natalia-marketing-department.

Каждый промпт = один шаг плейбука.

---

## ПРОМПТ 1 — SEO Keyword Map Builder (Шаг 1)

**Когда запускать:** один раз на старте + раз в неделю обновлять.

**Куда вставлять:** Claude Project с прикреплёнными `icp.md` + `offer.md` + `competitors.md`.

```
You are an expert SEO strategist. My business is natalia-marketing-department — 
an open-source set of 21 AI marketing agents for small business in Russia. 
Built on Claude Code. Free, MIT license. My target customer is small business 
owners, founders in early stage, solo experts (consultants, coaches, lawyers, 
psychologists, nutritionists), local businesses (dental clinics, barbershops, 
cafes, fitness studios), and freelance marketing agencies — all unable to 
afford a full-time marketer (which costs 80-200K rubles/month in Russia).

Give me 30 keyword clusters organized by intent: informational, navigational, 
and transactional. For each cluster, give me: the primary keyword (in Russian, 
how Russian speakers actually google), 3 supporting long-tail variations, 
estimated competition level (low/medium/high), and a one-sentence content 
angle I can own. Prioritize keywords where the searcher is close to making a 
buying decision or has a specific urgent problem. Output this as a numbered table.

Anti-keywords (don't propose):
- "ChatGPT для бизнеса" общее
- Технические про Anthropic API
- "Нанять маркетолога / SMM-щика"
- "Промт-инжиниринг" общий

After the table, give me:
1. Top 7 keywords I should attack first (1-line reasoning each)
2. Top 3 keywords with strong competitors but content gap I can win
3. 3 keywords that look attractive but don't pursue (and why)
```

---

## ПРОМПТ 2 — Full Article Brief and Draft Generator (Шаг 2)

**Когда запускать:** для каждого из топ-10 ключей из Промпта 1.

**Куда вставлять:** Claude Project с `voice.md` + `icp.md` + `offer.md`.

```
You are an expert content strategist and SEO writer. I need a complete article 
for the keyword: [ВСТАВЬ КЛЮЧ ИЗ ПРОМПТА 1].

Step 1: Write a title using this format — [Specific outcome] + [Timeframe or 
Method] + [For whom]. Make it under 65 characters. In Russian.

Step 2: Write an intro (150 words max) that opens with the exact problem the 
searcher has, names the promise of the article, and gives one specific proof 
point or stat. In Russian.

Step 3: Write a full article outline with H2 and H3 headers. Each section 
should answer a real question the reader has. Include a FAQ section with 
5 questions pulled from what people actually ask about this topic 
(check Yandex auto-suggest, vc.ru / Habr / Reddit comments).

Step 4: Write the full article (1,200 to 1,800 words) in Russian. Plain language. 
No jargon. Short paragraphs (1-3 sentences). End with a clear CTA to 
"Скачай 21 AI-маркетолога на GitHub. Бесплатно. MIT: 
https://github.com/nibrovkina-cyber/natalia-marketing-department"

My offer is: natalia-marketing-department — 21 open-source Claude Skills 
that replace a full marketing department for Russian small business. 
Built on Schwartz/Ogilvy/Hopkins methodology. Free, runs locally on 
Claude Code with Anthropic API ($5-30/month).

VOICE RULES (CRITICAL — see growth-system/voice.md):
- Short sentences. Max 15-20 words each.
- Paragraphs 1-3 sentences max.
- Address the reader as "ты", not "вы".
- Numbers beat adjectives. "21 агент" not "много инструментов".
- BANNED words: качественный, эффективный, оптимизировать, 
  решение, комплексный, уникальный, профессиональный, 
  best practices, в данной статье, стоит отметить.
- Personal experience via "я" where natural.
- Concrete names/cities/situations, not "один клиент".
- Methodology mentions (Ogilvy, Schwartz, Hopkins) where relevant.

After the article, output a META block:
- Final title
- Description 150 chars (for Yandex/YouTube)
- 5 keywords
- 5-7 hashtags
```

---

## ПРОМПТ 3 — LinkedIn Hook Generator (Шаг 3, для русского — TenChat)

**Когда запускать:** для каждой опубликованной статьи / каждого видео.

**Куда вставлять:** Claude Project с `voice.md` прикреплённым.

```
You are a TenChat (Russian LinkedIn) content strategist. I need a hook 
for a post about [ТЕМА статьи / видео / результата].

Write 5 hook options using this structure: 
[Non-obvious person or context] + [did something surprising] + 
[hyper-specific number] + [named tool] + [fast timeframe].

Rules:
- No adjectives like "потрясающий", "невероятный", "лучший".
- Lead with the result. Numbers up front.
- Use real or realistic numbers (no fake claims).
- Each hook must be under 2 lines (TenChat shows 2 lines before "show more").
- The reader should feel mild disbelief and want to know how it happened.
- In Russian.
- Address as "ты" or impersonal — never "вы" formal.

My topic is: [ОПИШИ результат / историю / инсайт].
My audience is: small business owners in Russia who can't afford a marketer 
and use natalia-marketing-department.

After 5 hooks — recommend the strongest one and explain why in 1 sentence.

Then write the full TenChat post (200-400 words) using the recommended hook:
- Hook in first 2 lines
- 3-4 paragraphs of unpacking
- Personal experience via "я"
- Link in last line: "Полная версия: [URL]"
- 3-5 hashtags at the very end
```

---

## Как использовать эти промпты по плану плейбука

### Неделя 1 (4 часа работы)

**Понедельник (1 час):**
1. Открой Claude Project, прикрепи 4 файла стратегии
2. Запусти ПРОМПТ 1
3. Получи 30 кластеров
4. Открой Яндекс/YouTube в инкогнито, верифицируй топ-7 руками
5. Сохрани топ-7 в `inputs/current-keywords.md`

**Вторник-четверг (3 часа):**
6. Запусти ПРОМПТ 2 на топ-3 ключа подряд
7. Получи 3 готовых статьи (1500 слов каждая)
8. Прочитай вслух, поправь голос
9. Опубликуй в vc.ru / TenChat / Дзен / на свой блог

**Пятница (1 час):**
10. На каждую статью запусти ПРОМПТ 3
11. Опубликуй TenChat-пост и Telegram-сообщение
12. Закрепи на день

### Неделя 2-8

Повторяй цикл. **2-3 публикации в неделю.** За 8 недель — 19+ публикаций. Согласно статье — это и приводит к 10K signups.

---

## Контрольный список после каждого запуска промпта

**После Промпта 1:**
- [ ] 30 кластеров получены?
- [ ] Топ-7 верифицированы руками на Яндексе/YouTube?
- [ ] Записаны в `inputs/current-keywords.md`?

**После Промпта 2:**
- [ ] Title под 65 символов?
- [ ] Intro 150 слов с конкретной болью?
- [ ] FAQ 5 вопросов?
- [ ] 1200-1800 слов?
- [ ] Запрещённых слов нет?
- [ ] Один CTA в конце?

**После Промпта 3:**
- [ ] 5 хуков под 2 строки каждый?
- [ ] Цифры в первой строке?
- [ ] Полный пост на 200-400 слов готов?
- [ ] Хэштеги в конце, не в теле?

---

## Что делать если промпт даёт плохой output

**Промпт 1 даёт общие ключи:**
→ Прикрепи ICP-сегмент конкретно. "Делай только под Сегмент 3 — локальный малый бизнес".

**Промпт 2 не звучит как ты:**
→ Прикрепи `voice-trainer.md` с anti-примерами. Запусти заново.

**Промпт 3 даёт скучные хуки:**
→ Дай ему **реальную цифру** в input. "Кейс: стоматология 12 → 47 заявок за 6 недель".
→ Без цифры хуки всегда серые.
