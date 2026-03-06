# VibeArt
Social network for creative people where they can share their creativity.

## Run

This project is containerized with Docker. Make sure you have Docker and Docker Compose installed.

### 1. Clone the repository
Since this project uses submodules for frontend and backend:
```bash
git clone --recursive [https://github.com/Bitsulov/VibeArt.git](https://github.com/Bitsulov/VibeArt.git)
cd VibeArt
```

### 2. Run the application 
Development Mode (Hot-reload, Vite dev server):
```
docker compose -p vibeart-dev -f tools/docker/docker-compose-dev.yml up -d
```
Production Mode (Optimized build, Nginx proxy):
```
docker compose -p vibeart-prod -f tools/docker/docker-compose-prod.yml up -d
```

## Technologies & Infrastructure
Containers:
1. Frontend: React 19 SPA served by Nginx (in prod).
2. Backend: (Coming soon) - Spring boot framework (Java).

**Frontend Stack**:
- TypeScript,
- React 19,
- Vite
- SCSS
- CSS Modules
- Redux Toolkit,
- Axios
- TanStack Query (React Query)
- I18n

## Project Structure
- `frontend/` — React application source code.
- `tools/docker/` — Docker configurations, Compose files, configs, volumes.

## Links
- [Vibeart Frontend](https://github.com/Bitsulov/VibeArt-frontend.git) - frontend repository
- [Vibeart BackEnd](https://github.com/Bitsulov/vibeart-backend.git) - backend repository
