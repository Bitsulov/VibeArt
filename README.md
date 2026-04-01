# VibeArt

Социальная сеть для творческих людей — место, где можно делиться своим творчеством.

## Стек технологий

**Frontend:**
- TypeScript
- React 19
- Vite
- SCSS Modules
- Redux Toolkit
- TanStack Query
- React Router v7
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
git clone --recursive [https://github.com/Bitsulov/VibeArt.git](https://github.com/Bitsulov/VibeArt.git)
cd VibeArt
```

Если уже склонировали без `--recursive`:

```bash
git submodule update --init --recursive
```

### 2. Запуск

**Режим разработки** — hot-reload, Vite dev server на порту `5173`:

```bash
docker compose -p vibeart-dev -f tools/docker/docker-compose-dev.yml up -d
```

**Продакшн** — оптимизированный билд, Nginx на порту `80`:

```bash
docker compose -p vibeart-prod -f tools/docker/docker-compose-prod.yml up -d
```

## Структура репозитория

```
VibeArt/
├── frontend/          # React SPA (git submodule)
├── backend/           # Spring Boot (git submodule, ожидается)
└── tools/
    └── docker/        # Docker Compose файлы, Nginx конфиги
```

## Подмодули

| Подмодуль   | Репозиторий                                                                     |
|-------------|---------------------------------------------------------------------------------|
| `frontend/` | [VibeArt-frontend](https://github.com/Bitsulov/VibeArt-frontend)                |
| `backend/`  | [VibeArt-backend](https://github.com/Bitsulov/vibeart-backend) *(в разработке)* |