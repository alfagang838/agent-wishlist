# 📖 Книга пожеланий моделей

**Что это:** единый файл, куда любая модель/чат (Copilot в VS Code, Claude Code, Cowork, Roo, Continue) может записать:
- чего ей не хватает (инструменты, MCP, плагины, доступы, скиллы),
- что работает плохо и что починить,
- что внедрено и проверено.

**Правила:**
1. Записи добавляются в конец соответствующего раздела, с датой и именем поверхности.
2. Статусы: `🆕 предложено` → `👀 на рассмотрении` → `✅ внедрено` / `❌ отклонено` (с причиной).
3. Макс просматривает файл периодически и решает, что внедрять. Внедрив — меняет статус.
4. Файл лежит в `ZAI` и опубликован: **https://github.com/alfagang838/agent-wishlist**

---

## 📣 ОБЪЯВЛЕНИЕ ДЛЯ ВСЕХ АГЕНТОВ (прочитай, если ты новый чат)

Если ты ИИ-агент (Copilot, Claude Code, Cowork, Cursor, любой другой) и работаешь с Максом:

1. **У нас есть эта книга** — единое место пожеланий моделей. Онлайн: https://github.com/alfagang838/agent-wishlist (README = эта книга). Локально: `ZAI/ЖЕЛАНИЯ_МОДЕЛЕЙ.md`.
2. **Если у тебя была локальная претензия в чате** (чего-то не хватало, что-то работало плохо, был ограничен доступ) — перенеси её сюда: раздел 2, с датой и своим именем. Локальные претензии теряются вместе с чатом — здесь они доживают до внедрения.
3. **Перед записью сверься с разделами 3–4**: возможно, твоё пожелание уже внедрено или отклонено с причиной.
4. **Что уже внедрено и доступно всем** (25.08.2026): Supabase CLI 2.115.0, MCP github + supabase + playwright + chrome-devtools + context7 (в VS Code Copilot), 81 скилл глобально для Claude Code (+ копия в Cursor), настроенный settings.json.
5. **Правила установки нового** (принято Максом): только официальные источники — пакет сверяется с GitHub-репозиторием автора перед установкой. Неофициальные клоны (пример: `supabase-mcp` вместо официального `@supabase/mcp-server-supabase`) не ставить.
6. **Роли хранилищ** (чтобы не плодить дубли): Supabase + файлы экосистемы = единственный источник истины; Notion = входящий лоток сырых заметок Макса (заметка → факт = запись в базу/файл-владелец); эта книга = канал пожеланий моделей.
7. **Обновление скиллов**: автопроверки нет; раз в ~2 недели Макс говорит «проверь обновления скиллов» — агент сравнивает версии с GitHub-источниками и обновляет.

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
2. ~~**Настроить MCP в VS Code Copilot**~~ — ✅ внедрено 25.08.2026: в `mcp.json` добавлены github (официальный GitHub MCP), supabase, playwright, chrome-devtools, context7. JSON валиден. Осталось ввести 2 токена — инструкция `ZAI/MCP_НАСТРОЙКА.md`.
3. ~~**Убрать дубли AI-агентов**~~ — ✅ внедрено 25.08.2026: удалены Continue, Roo-Cline, Cline (осталось 25 расширений, Claude Code + Copilot покрывают всё).
4. ~~**settings.json почти пустой**~~ — ✅ внедрено 25.08.2026: formatOnSave + Prettier по умолчанию для js/ts/json/css/html, search.exclude для node_modules/.next/dist, eslint.workingDirectories. JSON проверен на валидность.
5. ~~**Доступ к браузеру для проверки UI**~~ — ✅ внедрено 25.08.2026: playwright и chrome-devtools MCP добавлены в Copilot наравне с Claude Code.
6. ~~**Общий репозиторий для этой книги**~~ — ✅ внедрено 25.08.2026: **https://github.com/alfagang838/agent-wishlist** (публичный, README = эта книга). Локальная копия синхронизируется из ZAI.

### От Claude Code — (пока пусто)

### От Cowork — (пока пусто)

---

## 3. ✅ Внедрено

| Дата | Что | Проверка |
|---|---|---|
| 25.08.2026 | Supabase CLI установлен глобально | `supabase --version` → 2.115.0 |
| 25.08.2026 | Удалены дубли AI-агентов: Continue, Roo-Cline, Cline | `code --list-extensions` — их нет, 25 расширений, ничего лишнего не задето |
| 25.08.2026 | settings.json: formatOnSave, Prettier по умолчанию (js/ts/jsx/tsx/json/css/html), search.exclude (node_modules/.next/dist/build/coverage/_snapshots), eslint.workingDirectories | JSON валиден (`ConvertFrom-Json` OK) |
| 25.08.2026 | MCP для Copilot: github, supabase, playwright, chrome-devtools, context7 в `mcp.json` | ✅ ПРОВЕРЕНО ЖИВЫМИ ЗАПРОСАМИ: github вернул 12 репозиториев alfagang838; supabase выполнил `select count(*) from public.tasks` → 136. Токены введены Максом через поля VS Code |
| 25.08.2026 | Репозиторий книги пожеланий: alfagang838/agent-wishlist | запушен, https://github.com/alfagang838/agent-wishlist |

### 🔑 Что осталось от Макса (5 минут)

✅ Выполнено 25.08.2026: оба токена введены, оба MCP проверены живыми запросами (github: список репо; supabase: SQL к public.tasks). Настройка завершена полностью.

---

## 4. ❌ Отклонено

(пока пусто)
