# Docker_Tamplate_Java

A full-stack Docker template with React (Vite + Tailwind + DaisyUI + shadcn/ui) frontend and Java Spring Boot backend.

## 🚀 Features

- **Frontend**: React 18 + Vite + Tailwind CSS + DaisyUI + shadcn/ui components
- **Backend**: Java 17 + Spring Boot 3
- **Docker**: Multi-stage builds for optimized images
- **CI/CD**: Automatic Docker Compose build on every PR to main
- **Auto-updated README**: Merge information updated automatically

## 📁 Project Structure

```
├── frontend/                 # React + Vite frontend
│   ├── src/
│   │   ├── components/ui/   # shadcn/ui components
│   │   ├── lib/             # Utilities
│   │   ├── App.jsx          # Main application
│   │   └── main.jsx         # Entry point
│   ├── Dockerfile
│   ├── package.json
│   ├── tailwind.config.js
│   └── vite.config.js
├── backend/                  # Java Spring Boot backend
│   ├── src/main/java/
│   ├── Dockerfile
│   └── pom.xml
├── docker-compose.yml        # Docker orchestration
└── .github/workflows/        # CI/CD pipelines
    ├── docker-compose.yml   # Build on PR
    └── update-readme.yml    # Update merge info
```

## 🛠️ Quick Start

### Prerequisites
- Docker & Docker Compose
- Node.js 18+ (for local development)
- Java 17+ (for local development)

### Run with Docker Compose
```bash
# Build and start all services
docker compose up --build

# Access the application
# Frontend: http://localhost:80
# Backend API: http://localhost:8080/api/health
```

### Local Development

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

**Backend:**
```bash
cd backend
./mvnw spring-boot:run
```

## 🔐 Branch Protection

To protect the main branch and require PRs for all changes:

1. Go to **Settings** → **Branches**
2. Add a branch protection rule for `main`
3. Enable:
   - ✅ Require a pull request before merging
   - ✅ Require status checks to pass before merging
   - ✅ Require branches to be up to date before merging
   - ✅ Do not allow bypassing the above settings

## 🔄 CI/CD Workflows

### Docker Compose Build (on PR to main)
- Builds both frontend and backend Docker images
- Starts services with Docker Compose
- Tests backend health endpoint
- Tests frontend accessibility
- Runs automatically on every PR to `main`

### README Update (on merge to main)
- Captures merge information automatically
- Updates this README with:
  - Last merger name
  - Merge timestamp (hours, minutes, seconds)
  - Merge message/name
  - Commit SHA

## 📦 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/health` | GET | Health check |
| `/api/info` | GET | Application info |

## 🎨 Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend Framework | React 18 |
| Build Tool | Vite 5 |
| CSS Framework | Tailwind CSS 3 |
| UI Components | DaisyUI + shadcn/ui |
| Backend Framework | Spring Boot 3 |
| Language | Java 17 |
| Container | Docker |
| Orchestration | Docker Compose |
| CI/CD | GitHub Actions |