# CTF Autonomous Infrastructure Template (Based on PICT-CTF-Website-Frontend)

## 🎯 Goal
Build a fully autonomous CTF platform template for 100–150 participants, based on [PICT-CTF-WEBSITE-FRONTEND](https://github.com/ashawe/PICT-CTF-WEBSITE-FRONTEND), with a microservice backend in FastAPI and a SPA frontend in Angular.

## 🚀 Quick Start
```bash
git clone https://github.com/Alexd-y/ctf-template.git
cd ctf-template
chmod +x run.sh
./run.sh
```

## 🧩 Features
- ✅ User registration & JWT login
- ✅ Challenge listing and flag submission
- ✅ Leaderboard with Redis
- ✅ Start/end timer for CTF
- ✅ Admin panel (users, logs, challenges)
- ✅ Team support
- ✅ Telegram/Discord notification bot (optional)

## ⚙️ Stack
### Backend:
- FastAPI
- PostgreSQL
- Redis
- Celery + RabbitMQ
- JWT Auth

### Frontend:
- Angular + Tailwind CSS

### DevOps:
- Docker Compose (1-server setup)
- GitHub Actions (CI/CD)
- Nginx reverse proxy
- Optional: Prometheus + Grafana + Sentry

## 🧱 Architecture (Monolithic Docker Compose)
```
ctf-template/
├── auth-service/
├── challenge-service/
├── flag-service/
├── scoreboard-service/
├── admin-service/
├── frontend/
├── db/ (PostgreSQL)
├── redis/
├── rabbitmq/
├── docker-compose.yml
├── run.sh
├── setup-server.sh
└── .github/workflows/ci.yml
```

## 🐳 Docker Compose (core services)
See `docker-compose.yml`. Exposes:
- http://localhost:4200 → Angular UI
- http://localhost:8001 → Auth service
- http://localhost:8002 → Challenge service
- http://localhost:8003 → Flag validator
- http://localhost:8004 → Leaderboard
- http://localhost:8005 → Admin API

## 🔐 Admin endpoints
Accessible via `admin-service` REST API (`/admin/users`, `/admin/logs`)

## 📦 How to deploy on GitHub
```bash
git init
git remote add origin https://github.com/Alexd-y/ctf-template.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

## 📝 License
MIT License — free to use, extend, and host
