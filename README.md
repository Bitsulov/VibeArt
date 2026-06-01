# VibeArt

Социальная сеть для творческих людей — место, где можно делиться своим творчеством.

## Стек технологий

**Frontend:**
- TypeScript
- React 19
- React Router v7 (SPA + SSR)
- Vite
- SCSS Modules
- Redux Toolkit
- TanStack Query
- Axios
- i18n
- Vitest
- Playwright

**Backend** _(в разработке):_
- Java
- Spring Boot

**Инфраструктура:**
- Docker
- Docker Compose
- Nginx

## Быстрый старт

### 1. Клонирование

Проект использует git submodules для frontend и backend:

```bash
git clone --recursive https://github.com/Bitsulov/VibeArt.git
cd VibeArt
```

Если уже склонировали без `--recursive`:

```bash
git submodule update --init --recursive
```

### 2. Переменные окружения

Скопируй `.env.example` в `.env` и заполни переменные:

| Переменная      | Описание                                   |
|-----------------|--------------------------------------------|
| `URL_DEV`       | Публичный URL для режима разработки        |
| `URL_PROD`      | Публичный URL для производственной среды   |
| `API_BASE_DEV`  | Базовый URL API для режима разработки      |
| `API_BASE_PROD` | Базовый URL API для производственной среды |
| `EMAIL`         | Контактный email, отображаемый на сайте    |

```bash
cp .env.example .env
```

### 3. Запуск

**Режим разработки** — frontend-контейнер с hot-reload на порту `5173`:

```bash
docker compose -p vibeart-dev -f tools/docker/docker-compose-dev.yml --env-file .env up -d --build
```

**Производственная среда** — frontend-контейнер + Nginx-контейнер на порту `80`:

```bash
docker compose -p vibeart -f tools/docker/docker-compose-prod.yml --env-file .env up -d --build
```

## Структура репозитория

```
VibeArt/
├── frontend/          # React SPA + SSR (git submodule)
├── backend/           # Spring Boot (git submodule, ожидается)
└── tools/
    └── docker/        # Docker Compose файлы, Nginx конфиги
```

## Подмодули

| Подмодуль   | Репозиторий                                                                     |
|-------------|---------------------------------------------------------------------------------|
| `frontend/` | [VibeArt-frontend](https://github.com/Bitsulov/VibeArt-frontend)                |
| `backend/`  | [VibeArt-backend](https://github.com/Bitsulov/vibeart-backend) *(в разработке)* |
