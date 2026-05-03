# Pull Request

## Что меняется

<!-- Кратко: новый skill / fix / docs / showcase / адаптация / другое -->

## Почему

<!-- Какая проблема / задача решается -->

## Как тестировать

<!-- Если skill — какой промпт запустить, какой output ожидать -->

```
/natalia-skill пример входа
```

Ожидаемый output:
- ...

## Тип изменения

- [ ] 🆕 Новый skill
- [ ] 🐛 Bug fix
- [ ] 📚 Documentation
- [ ] 🎯 Showcase (реальный кейс)
- [ ] 🌍 Адаптация под другой рынок (Беларусь / Казахстан / EN-version / etc)
- [ ] 🔧 Refactor
- [ ] ⚡ Performance / cost optimization

## Чеклист перед merge

- [ ] Прочитала [CONTRIBUTING.md](../CONTRIBUTING.md)
- [ ] SKILL.md (если новый/изменённый skill) имеет валидный frontmatter (name + description + version)
- [ ] description в SKILL.md чёткий и однозначный (Claude применяет skill по нему)
- [ ] Voice rules соблюдены (нет "качественный" / "эффективный" / "оптимизировать")
- [ ] Локально протестировала через `cp -r skills/* ~/.claude/skills/` + перезапуск Claude Code
- [ ] Если showcase — есть реальные цифры

## Связанные issues

Closes #
