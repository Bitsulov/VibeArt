# CLAUDE.md

Этот файл содержит инструкции для Claude Code при работе с корневым репозиторием VibeArt.

## Что такое этот репозиторий

Корневой инфраструктурный репозиторий проекта VibeArt — социальной сети для творческих людей.
Содержит **только Docker-инфраструктуру** и связывает подмодули через git submodules.

## Зона ответственности

Работать только с файлами в этих директориях:
- `tools/docker/` — docker-compose файлы, Nginx конфиги, volumes
- `.github/` — CI/CD пайплайны (когда появятся)
- Корневые файлы: `README.md`, `CLAUDE.md`, `.gitmodules`

**Никогда не редактировать файлы внутри подмодулей** (`frontend/`, `main-service/`, `email-service/`).
Для работы с подмодулями — открывать их отдельно, у каждого свой CLAUDE.md.

## Структура проекта

- `frontend/` — React 19 SPA + SSR (подмодуль → vibeart-frontend)
- `main-service/` — Spring Boot / Java API (подмодуль → vibeart-service-api)
- `email-service/` — сервис отправки email (подмодуль → vibeart-service-email)
- `tools/docker/` — Docker Compose файлы и Nginx конфиги

## Запуск приложения

```bash
docker compose -p vibeart -f tools/docker/docker-compose-prod.yml --env-file .env up -d --build
```

## Git Workflow

- Не коммитить и не пушить напрямую в `main`
- Именование веток: `feature/<name>`
- Заголовок коммита: ≤ 50 символов, lowercase
- Тело коммита: строки ≤ 72 символа
- После обновления подмодуля — коммитить новый pointer из корневого репо отдельным коммитом в соответствующей ветке

## Запреты

- Не читать и не выводить содержимое `.env` и `.env.*` файлов
- Не редактировать код внутри `frontend/`, `main-service/` и `email-service/`
- Не запускать тесты подмодулей из корня — у каждого свой CI
