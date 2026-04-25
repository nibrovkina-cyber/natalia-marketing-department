# natalia · marketing department

**Бесплатный AI-маркетинговый отдел из 16 агентов** для малого и среднего бизнеса в России. Open source. MIT лицензия.

Скачивай → копируй в `~/.claude/skills/` → запускай в Claude Code. Никакого аккаунта, никакой подписки. Работает локально с твоим Anthropic API ключом.

> **Часть проекта [natalia.com](https://natalia.com)** — AI Marketing Studio Натальи Бровкиной. Это бесплатная версия. Платный hosted-инструмент с UI и оплатой через ЮKassa: [скоро](https://natalia.com/pricing).

---

## Что внутри

16 узких агентов на методологии **Ogilvy / Schwartz / Hopkins**:

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

Плюс мастер-skill `natalia` — оркестратор который знает обо всех 16.

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

Реальные кейсы из портфолио Натальи которые показаны в [YouTube-демо](https://natalia.com/gallery):

| Кейс | Метрика | Что сделали |
|---|---|---|
| **MEDEA Dent** · стоматология, Покровка, Москва | заявок **×3.4** за 90 дней | Hero с врачами вместо stock-отзывов, прозрачные цены, FAQ закрывающий 6 возражений |
| **Simbios Marketing** · агентство, Москва | конверсия в заявку **+58%** за 60 дней | Killer-headline «13 500 водителей таксопаркам за 1 800 ₽ за лида» вместо абстракций |

---

## Tier-ы продукта natalia.com

Эта open-source версия — **первый из трёх** уровней:

| Tier | Что | Цена |
|---|---|---|
| 🆓 **Бесплатно** (этот репо) | 16 skills локально, свой API ключ | 0 ₽ |
| 💼 **Инструмент** ([app.natalia.com](https://app.natalia.com)) | Hosted UI, brand memory, team mode, без своего API ключа | 2 990 ₽ / мес |
| 🤝 **Со мной** ([Telegram @NATASHABROVKINA](https://t.me/NATASHABROVKINA)) | Я лично делаю под ключ за 30 дней | 49 000 ₽ |

---

## Contributing

Pull request-ы приветствуются. Особенно:
- Новые showcase-кейсы (с твоего реального бизнеса, с цифрами)
- Адаптации под другие рынки (Беларусь, Казахстан)
- Перевод на английский для EN-аудитории
- Дополнительные business types в `BUSINESS_TYPES`

Issues тоже — если нашёл баг или хочешь обсудить новый агент.

---

## Author

**Наталья Бровкина**
- Сайт: [natalia.com](https://natalia.com)
- Telegram: [@NATASHABROVKINA](https://t.me/NATASHABROVKINA)
- YouTube: [@nataliabrovkina](https://youtube.com/@nataliabrovkina) *(скоро)*

## License

[MIT](LICENSE) — форкай, адаптируй под свой бренд, делись изменениями обратно. При использовании в коммерческих продуктах оставь упоминание «Powered by natalia.com» или ссылку на этот репо.

---

## Almost done?

Если у тебя получилось установить и запустить — **дай ⭐ репозиторию.** Это помогает другим предпринимателям его найти.

Если что-то не запустилось — открой [issue](https://github.com/nibrovkina-cyber/natalia-marketing-department/issues), я отвечаю в течение дня.
