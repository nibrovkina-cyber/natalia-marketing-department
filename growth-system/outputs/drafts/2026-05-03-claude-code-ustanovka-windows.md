# Установка Claude Code на Windows: пошаговая инструкция за 10 минут

Claude Code — терминальный клиент Claude от Anthropic. Бесплатный. Запускается на твоём компе, работает с твоими файлами.

Большинство гайдов в интернете — для macOS и Linux. Под Windows — путаница: то WSL, то Git Bash, то PowerShell. Я ставила Claude Code на трёх Windows-машинах — расскажу что реально работает.

После установки можно запускать готовые skills (включая мои 21 AI-агента для маркетинга из natalia-marketing-department).

---

## Что нужно перед установкой

1. **Windows 10 или 11** — на 7-8 не пробовала, скорее всего не пойдёт
2. **Anthropic API ключ** — оформляешь на [console.anthropic.com](https://console.anthropic.com), стартовый депозит $5 хватит на 100+ задач
3. **Node.js 18+** — нужен для Claude Code CLI
4. **30 минут времени** на первый запуск

---

## Способ 1 — Native Windows (рекомендую)

С весны 2026 Anthropic выпустила нативный Windows-инсталлятор. Раньше нужно было WSL — теперь работает прямо в PowerShell.

### Шаг 1 — установить Node.js

Скачай с [nodejs.org](https://nodejs.org) **LTS-версию** (на момент написания — Node 22). Запусти инсталлер. Все галочки по умолчанию.

Проверь после установки:

```powershell
node --version
npm --version
```

Должны показать версии. Если нет — перезагрузи PowerShell.

### Шаг 2 — установить Claude Code

Открой PowerShell **от имени администратора** (Win + X → Terminal Admin).

```powershell
npm install -g @anthropic-ai/claude-code
```

Установка займёт 2-3 минуты. После установки:

```powershell
claude --version
```

Должна появиться версия (типа `0.5.x`).

### Шаг 3 — настроить API ключ

```powershell
claude auth
```

Откроется браузер с авторизацией Anthropic. Войди в свой аккаунт → нажми "Authorize". Готово, ключ привязан.

Альтернатива — задать ключ переменной окружения:

```powershell
[Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "sk-ant-api03-...", "User")
```

### Шаг 4 — запустить Claude Code

```powershell
cd C:\путь\к\папке\проекта
claude
```

Откроется чат. Печатаешь задачу — Claude отвечает. Готово.

---

## Способ 2 — WSL (если способ 1 не работает)

Иногда Native Windows глючит на старых сборках 10. Тогда — WSL (Windows Subsystem for Linux).

### Шаг 1 — установить WSL

PowerShell от админа:

```powershell
wsl --install
```

Установит Ubuntu по умолчанию. Перезагрузи компьютер. Откроется Ubuntu, попросит создать username + пароль.

### Шаг 2 — внутри Ubuntu установить Node

```bash
sudo apt update
sudo apt install nodejs npm
node --version
```

Если версия старая (меньше 18):

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
```

### Шаг 3 — установить Claude Code

```bash
sudo npm install -g @anthropic-ai/claude-code
claude auth
```

Та же логика, но всё в Linux-окружении.

### Шаг 4 — где живут файлы

В WSL твои Windows-файлы доступны по пути `/mnt/c/`. Например:

```bash
cd /mnt/c/Users/имя/projects/мой-проект
claude
```

---

## Способ 3 — Git Bash (если оба выше не подходят)

На совсем старых Windows-сборках или корпоративных компах с заблокированным WSL — через Git Bash.

### Шаг 1 — установить Git Bash

[git-scm.com/download/win](https://git-scm.com/download/win). По умолчанию.

### Шаг 2 — установить Node через Git Bash

[nodejs.org](https://nodejs.org) → LTS, обычный инсталлер.

### Шаг 3 — Claude Code

В Git Bash:

```bash
npm install -g @anthropic-ai/claude-code
claude auth
```

Работает чуть медленнее чем native Windows, но стабильно.

---

## Установка готовых Skills (например, natalia-marketing-department)

Skills — это готовые AI-агенты которые делают конкретные задачи. У меня в open-source 21 агент для маркетинга малого бизнеса.

### Шаг 1 — клонировать репо

В PowerShell или WSL:

```powershell
git clone https://github.com/nibrovkina-cyber/natalia-marketing-department.git
cd natalia-marketing-department
```

### Шаг 2 — скопировать скиллы в папку Claude

**В PowerShell (Native Windows):**

```powershell
$src = ".\skills\"
$dst = "$env:USERPROFILE\.claude\skills\"
New-Item -ItemType Directory -Force -Path $dst
Copy-Item -Path "$src*" -Destination $dst -Recurse -Force
```

**В Git Bash или WSL:**

```bash
mkdir -p ~/.claude/skills
cp -r skills/* ~/.claude/skills/
```

### Шаг 3 — проверить что Claude видит скиллы

В Claude Code:

```
/help
```

Должны появиться все 21 команда: `/natalia-positioning`, `/natalia-copy`, `/natalia-landing` и т.д.

---

## Типичные ошибки и решения

### "claude: command not found"

Проблема: Node.js global path не в PATH.

**Решение PowerShell:**
```powershell
$env:PATH += ";$env:APPDATA\npm"
```

Или перезапусти PowerShell после установки npm-пакета.

### "Permission denied" при npm install -g

Запусти PowerShell от админа. Или используй WSL — там нет этой проблемы.

### "Cannot connect to Anthropic API"

Проверь интернет. Антивирусы иногда блокируют. Попробуй отключить временно.

### "Skills не видны через /help"

1. Проверь путь: `dir $env:USERPROFILE\.claude\skills` — должны быть папки `natalia-*`
2. Перезапусти Claude (`exit` → запустить заново)
3. Проверь что в каждой папке есть файл `SKILL.md`

### "$0.30 за один запуск — это нормально?"

Зависит от размера задачи. Для лендинга на 1500 слов с разбором — $0.50-2 это норма. Для короткого вопроса — $0.05.

Чтобы видеть расходы:

```powershell
claude usage
```

Покажет сколько потрачено за месяц.

---

## Сколько стоит работа Claude Code в месяц

На средний объём задач для маркетинга малого бизнеса — **$5-30 в месяц** на Anthropic API.

Конкретные цифры:
- Один бриф клиента: $0.30-0.50
- Полный лендинг с разбором: $1-2
- Welcome-серия из 5 писем: $0.50-1
- 1500-словная SEO-статья: $0.30-0.80

Если плотно работаешь по 2-3 клиентам — $20-30/мес.

Для сравнения: ChatGPT Plus — $20/мес фиксированно. Claude Code дешевле на маленьком объёме и масштабируется по факту.

---

## Что делать дальше после установки

1. **Создать папку клиента** с файлом `brand-memory.json` (адрес, цены, ICP, что говорить и что запрещено)
2. Запустить первый скилл: `/natalia-positioning` или `/natalia-landing https://сайт-клиента.ру`
3. Получить результат за 5-15 минут
4. Прочитать [README natalia-marketing-department](https://github.com/nibrovkina-cyber/natalia-marketing-department) для полного списка команд

---

## FAQ

**Можно без VPN из РФ?**
Да. Anthropic API работает с РФ напрямую. Оплачивать тоже можно — российские карты не подходят, но доступны Wise, Paysend, или зарубежные карты.

**Сколько ОЗУ нужно?**
Минимум 8 ГБ. Лучше 16. Сам Claude Code не тяжёлый, но WSL + IDE + браузер сжирают память.

**Работает на Mac M1/M2?**
Да. Native через `npm install -g @anthropic-ai/claude-code`. Гайд тот же что для Linux.

**Skills natalia-* подходят только для маркетинга?**
Да. Это специализированный набор. Для другого домена — пиши свои skills (формат простой) или ищи на GitHub по тегу `claude-skills`.

**Можно ли запускать Claude Code в фоне?**
Можно через CI/CD. Anthropic выпустил Claude Code Action для GitHub Actions — запускается на пуше. Но для маркетинга обычно интерактивный режим достаточно.

---

## Скачай 21 AI-маркетолога после установки

**Open source. MIT. Бесплатно.**

https://github.com/nibrovkina-cyber/natalia-marketing-department

Установка Claude Code — 10 минут. Установка скиллов — 5 минут. Первый бриф клиента — 15 минут после старта.

---

## META

- **Title:** Установка Claude Code на Windows: пошаговая инструкция за 10 минут
- **Description:** 3 способа установки Claude Code на Windows: Native, WSL, Git Bash. Решения типичных ошибок. Установка готовых skills (natalia-marketing-department).
- **Keywords:** claude code установка windows, claude code на windows, как установить claude code, claude code wsl, anthropic claude windows
- **Hashtags:** #claudecode #anthropic #windows #установка #claude
