# Telegram Client Bot — QA Project

## Summary
Ручное и API‑тестирование Telegram‑бота (webhook). Фокус — стабильность диалога, обработка ошибок и валидации входных данных, корректная маршрутизация команд.

## Key results
- Выявлены критические и мажорные дефекты в обработке ошибок и устойчивости webhook (подробности в `tests/`).
- Подготовлены структурированные артефакты: тест‑стратегия, тест‑план, тест‑кейсы, чек‑листы, скриншоты.
- Настроена Postman‑коллекция для API‑проверок и регресса.

## Artefacts
- `tests/test_strategy.md` — стратегия тестирования
- `tests/test_plan.md` — тест‑план (объём, окружение, риски)
- `tests/test_cases.md` — тест‑кейсы (позитив/негатив/edge)
- `tests/checklist.xlsx` — чек‑лист (в формате .xlsx)
- `tests/Telegram bot.postman_collection.json` — Postman‑коллекция (REST)
- `tests/screenshots.md` + `screenshots/` — визуальные доказательства
- `tests/test_execution_summary.md` — сводка прогона тестов (этот файл добавлен для наглядности)
- `tests/bug_report_template.md`, `tests/bug-001_example.md` — шаблон и пример баг‑репорта

## How to run API checks (локально)
> Требуется Node.js и Newman (HTML‑reporter по желанию).
```bash
npm install -g newman newman-reporter-html
newman run "tests/Telegram bot.postman_collection.json"   -r html --reporter-html-export tests/report.html
# Откройте tests/report.html в браузере
```

## Notes
- Если отчёт `tests/report.html` отсутствует в репозитории, сгенерируйте его локально командой выше.
- Пример баг‑репорта носит демонстрационный характер. В боевой проект добавляю фактические дефекты по результатам прогона.
