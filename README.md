# 🌍 TrailWise — Intelligent Tour Management & Travel Operations Ecosystem

[![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core_8-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![React 19](https://img.shields.io/badge/React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Flutter](https://img.shields.io/badge/Flutter_3-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Groq LLM](https://img.shields.io/badge/AI_Coordinator-Groq_Cloud-F05032?style=for-the-badge)](https://groq.com/)
[![Tests](https://img.shields.io/badge/Tests-1673_Passing-2ea44f?style=for-the-badge)](#-testing--code-quality)

> **TrailWise** is a production-grade, multi-platform travel management and planning system. It bridges travelers, tour guides, drivers, fleet coordinators, and operations managers through real-time operational workflows, automated pricing engines, and an autonomous **AI Coordinator Agent** featuring human-in-the-loop exception handling.

---

## 🚀 Live Demos & Deployments

| Component | Platform / Host | Access Link |
| :--- | :--- | :--- |
| **🌐 Web Operations & Traveler Console** | Vercel (React 19 + TypeScript + Vite) | [**Open Web App**](https://trailwise-xi.vercel.app/) |
| **⚡ Backend API & Services** | Render (ASP.NET Core 8 Web API) | [**View API Service**](https://trailwise.onrender.com) |
| **📖 Interactive API Documentation** | Swagger / OpenAPI | [**Explore Swagger UI**](https://trailwise.onrender.com/swagger) |
| **📱 Mobile Application (Android)** | Flutter Release Bundle | [**Download APK (Google Drive)**](https://drive.google.com/drive/folders/1O3mV2JGF5MCdc4SF8WNbP16otNSG9Tdn) |

### 🔑 Demo Credentials

| Role | Email | Password | Primary Capabilities |
| :--- | :--- | :--- | :--- |
| **Administrator** | `admin@trailwise.local` | `ChangeMe123!` | System-wide RBAC, staff credentials, package catalogs |
| **Operations Manager** | `ops@trailwise.local` | `ChangeMe123!` | AI proposal reviews, refunds, discounts, booking approvals |
| **Fleet Coordinator** | `fleet@trailwise.local` | `ChangeMe123!` | Driver & vehicle schedule allocation, roster monitoring |
| **Tour Guide** | `guide@trailwise.local` | `ChangeMe123!` | Availability calendar, assigned tour manifests |
| **Driver** | `driver@trailwise.local` | `ChangeMe123!` | Real-time driving tasks, vehicle inspections, contacts |
| **Traveler** | *Self-Register* | *Your choice* | Browse tour tiers, book trips, view agent quotes |

---

## ✨ Key Engineering Highlights

### 🤖 1. Autonomous AI Coordinator Agent (Groq Cloud LLM)
- **Natural Language Preference Extraction**: Uses LLM agents to parse unstructured traveler requests (e.g., dietary restrictions, mobility needs, budget constraints) into structured booking criteria.
- **Dynamic Resource Matching**: Evaluates package tiers, available fleet capacities, and tour guide proficiencies to synthesize custom itinerary proposals.
- **Human-in-the-Loop Safeguards**: Detects anomalies (budget deficits, large-group overcapacity, refund escalations) and halts execution for Operations Manager approval with complete audit trails.

### 🏢 2. Comprehensive 6-Role Portal Architecture
- **Traveler Portal**: Package search with interactive maps, multi-tier pricing breakdown, instant booking request submission, and refund status tracking.
- **Operations Console**: Approval queues, AI workflow state inspector, financial transaction logs, and rule-based discount management.
- **Fleet Management**: Interactive dispatch board, vehicle allocation grid (AC, seat capacity, status), and driver duty roster.
- **Guide & Driver Hubs**: Dedicated calendar scheduling, tour manifest reviews, and one-tap communication dialers.

### 🧪 3. Rigorous Multi-Platform Test Coverage
- **1,673 Automated Tests** ensuring rock-solid stability across the entire stack:
  - **889 Backend Tests** (`xUnit`, `Moq`, `EF Core InMemory`): Clean architecture enforcement, API contract tests, and concurrency safety.
  - **471 Web Tests** (`Vitest`, `@testing-library/react`): Component state testing, mock authentication flows, and design system token validation.
  - **313 Mobile Tests** (`flutter test`): Golden & widget tests, responsive layout constraints, and network failure fallback handling.

---

## 🛠️ Technology Stack

```
├── Backend API      │ ASP.NET Core 8 Web API, Entity Framework Core 8, Npgsql
├── Database         │ PostgreSQL 16 (Local Docker container or Supabase cloud instance)
├── Frontend Web     │ React 19, TypeScript, Vite, Tailwind CSS v4, Lucide Icons, Leaflet Maps
├── Mobile App       │ Flutter 3, Dart, Provider state management, URL Launcher
├── AI Integration   │ Groq Cloud API (Llama 3 / Mistral LLM extraction & summarization)
├── Authentication   │ Secure JWT (JSON Web Tokens) with role-based claims & refresh flows
└── DevOps & Tooling │ Docker Compose, Multi-stage Dockerfiles, ESLint/Oxlint, Vitest
```

---

## 🏗️ Architecture & Project Structure

```
MyTailWiseProject/
├── backend/
│   ├── src/TrailWise.Domain/          # Core entities, value objects, domain logic
│   ├── src/TrailWise.Infrastructure/  # EF Core context, Postgres migrations, DbSeeder
│   ├── src/TrailWise.Api/             # Web API endpoints, JWT auth, Coordinator Agent
│   └── tests/TrailWise.Api.Tests/     # 889 unit & integration test suites
├── frontend-web/                      # React 19 + TypeScript + Vite web console
│   ├── src/api/                       # Axios client with authenticated interceptors
│   ├── src/components/                # Reusable UI system (modals, forms, maps, tables)
│   ├── src/pages/                     # Role-scoped views (Admin, Ops, Fleet, Guide, Driver)
│   └── src/theme/                     # Design tokens & dark/light theme support
├── frontend-mobile/                   # Flutter cross-platform mobile app
│   ├── lib/api/                       # Dio/HTTP client with token renewal
│   ├── lib/screens/                   # Traveler booking & driver task execution screens
│   └── test/                          # 313 unit, widget, and mock API tests
└── docker-compose.yml                 # Unified dev environment (PostgreSQL + API + Web)
```

---

## ⚡ Quickstart (Local Development)

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Node.js 20+](https://nodejs.org/)
- [Flutter SDK](https://docs.flutter.dev/get-started/install)

### 1. Run Everything with Docker Compose

```bash
# 1. Clone repository
git clone https://github.com/JaniduKasuntha/MyTailWiseProject.git
cd MyTailWiseProject

# 2. Configure environment
cp .env.example .env

# 3. Start PostgreSQL, API, and Web console
docker compose up --build
```
- **Web App**: `http://localhost:5173`
- **Backend API & Swagger**: `http://localhost:5080/swagger`

---

### 2. Run the Mobile App (Flutter)

The Flutter mobile app runs natively against your local API:

```bash
cd frontend-mobile
flutter pub get
flutter run --dart-define=API_BASE_URL=http://localhost:5080
```

---

### 3. Running Services Standalone (Outside Docker)

<details>
<summary><b>Click to expand standalone commands</b></summary>

#### Backend:
```bash
cd backend
dotnet ef database update --project src/TrailWise.Infrastructure --startup-project src/TrailWise.Api
dotnet run --project src/TrailWise.Api
```

#### Frontend Web:
```bash
cd frontend-web
npm install
npm run dev
```

#### Database Switching (Local Postgres ↔ Supabase):
To use a managed Supabase database instead of local Docker PostgreSQL, set the `CONNECTION_STRING` variable in `.env` to your Supabase connection string. EF Core migrations run automatically on startup.
</details>

---

## 🧪 Testing & Code Quality

You can verify the entire test matrix across all platforms locally:

```bash
# 1. Backend tests (889 passing tests)
cd backend
dotnet test

# 2. Frontend Web tests (471 passing tests)
cd frontend-web
npm test
npm run lint

# 3. Mobile tests (313 passing tests)
cd frontend-mobile
flutter test
flutter analyze
```

---

## 📄 License & Credits
Developed as part of the **TrailWise Smart Tour Management & Travel Planning System**. All rights reserved.
