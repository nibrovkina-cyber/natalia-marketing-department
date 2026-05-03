# Развёртывание natashabrovkina.com — пошаговая инструкция

После того как ты купила домены на Reg.ru, делаешь это по порядку. Каждый шаг — 5-15 минут. Общее время: ~1 час до запуска.

---

## ЭТАП 1 — Подтверждение доменов на Reg.ru (15 минут после оплаты)

Reg.ru присылает email "Подтверждение администратора домена". Открой → нажми ссылку. **Если не подтвердить за 15 дней — ICANN заблокирует домен.**

Делаешь это для каждого купленного домена.

---

## ЭТАП 2 — Vercel (если ещё не деплоила)

### 2.1 — Создаёшь аккаунт Vercel

1. Открой → https://vercel.com/signup
2. **Sign up with GitHub** (твой GitHub `nibrovkina-cyber`)
3. Free план достаточен — $0/мес для small-traffic

### 2.2 — Импортируешь проект

1. В Vercel dashboard → **Add New → Project**
2. **Import Git Repository** — найди `ai-marketing-natalia` в списке (или загрузи через `Continue with GitHub`)
3. **Framework Preset:** Next.js (определит автоматически)
4. **Root Directory:** оставь по умолчанию (`./`)
5. **Build Command:** `next build` (уже в [vercel.json](../../ai-marketing-natalia/vercel.json))
6. **Region:** Frankfurt (`fra1`) — ближе к РФ-аудитории, уже задано в vercel.json

### 2.3 — Environment Variables (КРИТИЧНО — без этого /tool не заработает)

В разделе **Environment Variables** перед деплоем добавь:

| Имя | Значение | Откуда взять |
|---|---|---|
| `ANTHROPIC_API_KEY` | `sk-ant-api03-...` | https://console.anthropic.com/settings/keys |
| `FIRECRAWL_API_KEY` | `fc-...` (опционально) | https://www.firecrawl.dev/app/api-keys |
| `TELEGRAM_BOT_TOKEN` | `123:ABC...` (опционально, для уведомлений с waitlist) | @BotFather в Telegram |
| `TELEGRAM_CHAT_ID` | `-1001234567890` | Через @userinfobot или ID твоего канала |
| `WAITLIST_WEBHOOK_URL` | url (опционально) | Если хочешь форвардить заявки в CRM |

**Минимум для запуска:** только `ANTHROPIC_API_KEY`. Остальное — позже.

⚠️ Anthropic ключ — у тебя должен быть свой с балансом. Один лендинг = ~$0.05 расхода. Стартовый депозит $5 → ~100 генераций.

### 2.4 — Deploy

Нажимаешь **Deploy** → ждёшь 2-3 минуты. Получаешь временный URL: `ai-marketing-natalia-xxx.vercel.app`. Откроешь — увидишь свой сайт работающим.

---

## ЭТАП 3 — Подключение `natashabrovkina.com` к Vercel

### 3.1 — В Vercel

1. Project → **Settings → Domains**
2. Поле "Add Domain" → введи `natashabrovkina.com` → **Add**
3. Vercel покажет инструкцию для DNS. Запомни два варианта:

**Вариант A (рекомендую) — Vercel-managed DNS:**
- Vercel показывает 2 nameservers, например:
  ```
  ns1.vercel-dns.com
  ns2.vercel-dns.com
  ```

**Вариант B — A-запись:**
- A-запись apex `natashabrovkina.com` → `76.76.21.21`
- CNAME `www.natashabrovkina.com` → `cname.vercel-dns.com`

### 3.2 — В Reg.ru

1. Войди в личный кабинет → **Мои домены → natashabrovkina.com**
2. Кликни домен → **DNS-серверы и зона**

**Если выбрала Вариант A (рекомендую):**
- Раздел "Управление DNS-серверами"
- Замени `ns1.reg.ru` / `ns2.reg.ru` на `ns1.vercel-dns.com` / `ns2.vercel-dns.com`
- Сохранить

**Если Вариант B:**
- Раздел "Управление зоной"
- Удали все A/CNAME для @ и www
- Добавь:
  - `@` → A → `76.76.21.21`
  - `www` → CNAME → `cname.vercel-dns.com`
- Сохранить

### 3.3 — Жди DNS пропагации

10 минут — 1 час обычно. Иногда до 24 часов. Проверить можно: https://www.whatsmydns.net/#A/natashabrovkina.com

Когда DNS прописан → Vercel сам выдаст Let's Encrypt SSL → сайт открывается на `https://natashabrovkina.com`.

---

## ЭТАП 4 — Подключение `nataliyabrovkina.com` как 301-редирект

### 4.1 — В Vercel

1. Project → **Settings → Domains**
2. **Add Domain** → `nataliyabrovkina.com` → **Add**
3. Vercel покажет: "Redirect to natashabrovkina.com" — оставь эту опцию включённой
4. **Redirect Status Code:** 301 (Permanent)

### 4.2 — В Reg.ru

Делаешь то же что в шаге 3.2 — направляешь DNS `nataliyabrovkina.com` на Vercel.

**Результат:** кто-то набирает `nataliyabrovkina.com` → 301 → `natashabrovkina.com`. Поисковики правильно склеют SEO-вес.

### 4.3 — То же для `natashabrovkina.ru`

Если купила — добавь в Vercel как ещё один домен с 301-редиректом.

---

## ЭТАП 5 — Проверка после запуска (5 минут)

Открой и убедись:

1. **`https://natashabrovkina.com`** → главная грузится
2. **`/tool`** → /tool страница, 16 агентов виден
3. **`/pricing`** → 3 тарифа видны
4. **`/waitlist`** → форма работает (попробуй отправить тестовый email)
5. **`/method`** → методология грузится
6. **`/gallery`** → 2 кейса (medea-dent, simbios)
7. **`https://nataliyabrovkina.com`** → редиректит на natashabrovkina.com
8. **OG Image:** открой `https://www.opengraph.xyz/url/https%3A%2F%2Fnatashabrovkina.com` — превью для соцсетей должно быть нормальным

**Если /tool не работает** → проверь, что `ANTHROPIC_API_KEY` действительно добавлен в Vercel env vars (Settings → Environment Variables).

---

## ЭТАП 6 — После запуска

### 6.1 — README репозитория

Ссылка `https://natashabrovkina.com` в [natalia-marketing-department/README.md:7](../README.md#L7) теперь работает. Проверь — открой README на GitHub, кликни ссылку.

### 6.2 — YouTube описание

В описании твоего видео `https://www.youtube.com/watch?v=UrU_tapUIxM` обнови ссылки:
- Замени `https://natashabrovkina.com` (которая раньше не работала) — теперь работает
- Добавь ссылку на GitHub-репо (если ещё нет)
- Добавь pinned comment с CTA

Текст для pinned-comment + описания — в [ai-marketing-natalia/content/youtube-description.md](../../ai-marketing-natalia/content/youtube-description.md).

### 6.3 — Публикация постов

Готовый distribution-pack: [growth-system/outputs/distribution-packs/2026-05-03-claude-dlya-marketinga-FINAL.md](outputs/distribution-packs/2026-05-03-claude-dlya-marketinga-FINAL.md)

CTA в постах уже настроен на трёхступенчатую воронку:
- YouTube видео (главное)
- GitHub репо
- natashabrovkina.com/waitlist

---

## Что может пойти не так — решения

**"DNS не пропагируется 6+ часов"**
→ Проверь что в Reg.ru ПРАВИЛЬНО заменены NS. Иногда Reg.ru держит кеш своих NS — попробуй "Сбросить кеш" в личном кабинете.

**"Vercel показывает Invalid Configuration на домене"**
→ Подожди 30 минут после DNS изменения. Если не помогло — проверь nslookup `natashabrovkina.com` локально, покажет ли Vercel IP.

**"/tool отвечает ошибкой Anthropic API"**
→ В Vercel → Settings → Environment Variables → проверь что ANTHROPIC_API_KEY валидный (попробуй curl с этим ключом). Иногда после добавления переменной нужен **redeploy** (Project → Deployments → ... → Redeploy).

**"301-редирект с nataliyabrovkina не работает"**
→ Проверь что в Vercel у этого домена включена опция "Redirect to natashabrovkina.com". Если включена — подожди DNS пропагацию.

---

## Минимальный сценарий (если что-то идёт не по плану)

Если по какой-то причине Vercel не работает — fallback:

1. **На Reg.ru** настрой простой редирект `natashabrovkina.com` → твой YouTube канал @NateBrovk. Это работает сразу, без хостинга. Все ссылки в постах ведут на YouTube — он растёт.

2. Параллельно решаешь Vercel-проблему. Когда заработает — переключаешь редирект на свой Next.js сайт.

Это даёт тебе **возможность публиковать посты сегодня даже если хостинг не готов завтра.**
