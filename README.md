# 📖 Книга пожеланий моделей

**Что это:** единый файл, куда любая модель/чат (Copilot в VS Code, Claude Code, Cowork, Roo, Continue) может записать:
- чего ей не хватает (инструменты, MCP, плагины, доступы, скиллы),
- что работает плохо и что починить,
- что внедрено и проверено.

**Правила:**
1. Записи добавляются в конец соответствующего раздела, с датой и именем поверхности.
2. Статусы: `🆕 предложено` → `👀 на рассмотрении` → `✅ внедрено` / `❌ отклонено` (с причиной).
3. Макс просматривает файл периодически и решает, что внедрять. Внедрив — меняет статус.
4. Файл лежит в `ZAI` — рабочей зоне агента. При желании можно вынести в отдельный репозиторий и подключить ко всем чатам.

---

## 1. Что уже есть (аудит 25.08.2026)

### CLI на машине
| Инструмент | Версия | Статус |
|---|---|---|
| git | 2.55.0 | ✅ |
| node | 26.5.0 | ✅ |
| npm | 11.17.0 | ✅ |
| python | 3.14.7 | ✅ |
| gh (GitHub CLI) | 2.98.0 | ✅ |
| vercel | 59.5.0 | ✅ |
| supabase | — | ❌ не установлен |

### Расширения VS Code
Claude Code, GitLens, GitHub PR & Actions, Tailwind IntelliSense, ESLint, Prettier, Path/NPM Intellisense, Python + Pylance + Debugpy, Error Lens, Todo Tree, dotenv, EditorConfig, Markdown All in One, Material Icons, Spell Checker, Thunder Client, Peacock, Auto Rename Tag, Git History, Supabase Extension, а также три конкурирующих AI-агента: **Continue, Roo-Cline, Cline**.

### Скиллы
~60 скиллов в `~/.claude/skills` (GSAP-набор, дизайн-набор, TDD, debugging, planning и др.) + 10 дизайн-скиллов в OpengravityProjects.

### MCP
Только **playwright** (в Claude). VS Code Copilot MCP не настроен.

---

## 2. 🆕 Пожелания (открытые)

### От Copilot (VS Code), 25.08.2026

1. ~~**Установить Supabase CLI**~~ — ✅ внедрено 25.08.2026 (`supabase --version` → 2.115.0, см. раздел 3).
2. **Настроить MCP в VS Code Copilot** — сейчас есть только playwright в Claude Code. Хочется:
   - `github` MCP (issues, PR, поиск по репо),
   - `supabase` MCP (запросы к живой базе из чата),
   - `context7` MCP (свежая документация библиотек вместо устаревших знаний).
   👀 на рассмотрении — требует ключей/решения Макса.
3. ~~**Убрать дубли AI-агентов**~~ — ✅ внедрено 25.08.2026: удалены Continue, Roo-Cline, Cline (осталось 25 расширений, Claude Code + Copilot покрывают всё).
4. ~~**settings.json почти пустой**~~ — ✅ внедрено 25.08.2026: formatOnSave + Prettier по умолчанию для js/ts/json/css/html, search.exclude для node_modules/.next/dist, eslint.workingDirectories. JSON проверен на валидность.
5. **Доступ к браузеру для проверки UI** — playwright MCP есть только у Claude Code; Copilot в VS Code им не пользуется. Либо настроить тот же MCP для Copilot, либо принять, что визуальную приёмку делает Claude Code.
6. **Общий репозиторий для этой книги** — чтобы любой чат мог ссылаться на неё по URL и предлагать PR с пожеланиями. Кандидат: `alfagang838/agent-wishlist`.

### От Claude Code — (пока пусто)

### От Cowork — (пока пусто)

---

## 3. ✅ Внедрено

| Дата | Что | Проверка |
|---|---|---|
| 25.08.2026 | Supabase CLI установлен глобально | `supabase --version` → 2.115.0 |
| 25.08.2026 | Удалены дубли AI-агентов: Continue, Roo-Cline, Cline | `code --list-extensions` — их нет, 25 расширений, ничего лишнего не задето |
| 25.08.2026 | settings.json: formatOnSave, Prettier по умолчанию (js/ts/jsx/tsx/json/css/html), search.exclude (node_modules/.next/dist/build/coverage/_snapshots), eslint.workingDirectories | JSON валиден (`ConvertFrom-Json` OK) |

---

## 4. ❌ Отклонено

(пока пусто)
