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

**API** _(в разработке):_
- Java
- Spring Boot

**Email-service:**
- Java 25
- Spring Boot 4.0
- Spring AMQP (RabbitMQ)
- Spring Mail

**Инфраструктура:**
- Docker
- Docker Compose
- Nginx

## Быстрый старт

### 1. Клонирование

Проект использует git submodules:

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

| Переменная                 | Описание                                  |
|----------------------------|---------------------------------------------|
| `URL`                      | Публичный URL сайта                          |
| `API_BASE`                 | Базовый URL API сервиса                      |
| `SUPPORT_EMAIL`            | Контактный email, отображаемый на сайте      |
| `EMAIL_PASSWORD`           | Пароль почтового аккаунта для email-service  |
| `CRYPTO_KEY`               | Ключ шифрования для frontend                 |
| `DB_NAME`                  | Имя базы данных Postgres                     |
| `DB_URL`                   | Адрес базы данных для main-service           |
| `DB_USERNAME`              | Имя пользователя базы данных                 |
| `DB_PASSWORD`              | Пароль пользователя базы данных              |
| `RABBIT_MQ_HOST`           | Хост RabbitMQ                                |
| `RABBIT_MQ_USERNAME`       | Имя пользователя RabbitMQ                    |
| `RABBIT_MQ_PASSWORD`       | Пароль пользователя RabbitMQ                 |
| `RABBIT_MQ_VHOST`          | Virtual host RabbitMQ                        |
| `JWT_SECRET_KEY`           | Секретный ключ для подписи JWT               |
| `JWT_ACCESS_TIME`          | Время жизни access-токена (мс)               |
| `JWT_REFRESH_TIME`         | Время жизни refresh-токена (мс)              |
| `PGADMIN_DEFAULT_EMAIL`    | Email для входа в pgAdmin                    |
| `PGADMIN_DEFAULT_PASSWORD` | Пароль для входа в pgAdmin                   |

```bash
cp .env.example .env
```

### 3. Запуск

Для запуска необходим docker-compose:

```bash
docker compose -p vibeart -f tools/docker/docker-compose-prod.yml --env-file .env up -d --build
```

## Структура репозитория

- `frontend/` — React SPA + SSR (git submodule)
- `main-service/` — Spring Boot API (git submodule)
- `email-service/` — сервис отправки email (git submodule)
- `tools/docker/` — Docker Compose файл, Nginx конфиг

## Подмодули

| Подмодуль        | Репозиторий                                                                |
|------------------|----------------------------------------------------------------------------|
| `frontend/`      | [VibeArt-web-frontend](https://github.com/Bitsulov/vibeart-web-frontend)   |
| `main-service/`  | [VibeArt-api-service](https://github.com/Bitsulov/vibeart-service-api)     |
| `email-service/` | [VibeArt-email-service](https://github.com/Bitsulov/vibeart-service-email) |
