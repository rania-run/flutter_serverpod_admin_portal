# Serverpod Admin Portal Server

This is the **Serverpod backend** for the Admin Portal. It provides endpoints, services, database models, and integrations (GCP, SendGrid).

---

## ✨ Features
- REST/gRPC endpoints for admin operations
- Business logic for authentication, notifications, and integrations
- Database models and migrations
- Integration with Google Cloud Platform and SendGrid

---

## 🛠 Requirements
- Dart 3.7+
- PostgreSQL (via Docker or Cloud SQL)
- Redis (via Docker)
- Serverpod CLI
- Docker (for local development)

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd serverpod_admin_portal_server
```

### 2. Install Serverpod CLI
```bash
dart pub global activate serverpod_cli
```

### 3. Start PostgreSQL and Redis (Docker)
```bash
docker compose up --build --detach
```

### 4. Apply database migrations
```bash
dart bin/main.dart --apply-migrations
```

### 5. Run the server
```bash
dart bin/main.dart
```

The server will be available at [http://localhost:8080](http://localhost:8080)

### 6. Stop services
- Stop the server: `Ctrl-C`
- Stop Docker services:
```bash
docker compose stop
```

---

## 🗄️ Database & Migrations
- Database models are defined in `models/` (YAML files)
- Migrations are managed in `migrations/`
- Use the Serverpod CLI to generate and apply migrations

---

## 🔑 Configuration & Secrets
- Config files:
  - `config/local.yaml`
  - `config/development.yaml`
  - `config/staging.yaml`
  - `config/production.yaml`
- Secrets are managed via **GCP Secret Manager** in non-local environments
- Example environment variables:
  - `DATABASE_URL`
  - `REDIS_URL`
  - `SENDGRID_API_KEY`

---

## 📂 Project Structure
- `endpoints/` – REST/gRPC endpoints
- `services/` – Business logic (auth, notifications, integrations)
- `models/` – Database models (YAML → Dart generated)
- `migrations/` – SQL migrations
- `config/` – Environment configuration files
- `bin/` – Main server entry point

---

## 🧪 Testing
- To run tests:
```bash
dart test
```
- Add your tests in the `test/` directory

---

## 🛠 Troubleshooting
- Ensure Docker is running for local Postgres/Redis
- Check that all environment variables are set
- For migration issues, verify your YAML model definitions
- For more help, see [Serverpod Documentation](https://docs.serverpod.dev/)

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License
[MIT](LICENSE)

---

## 📚 References
- [Serverpod Documentation](https://docs.serverpod.dev/)
- [Dart Language](https://dart.dev/)
- [Docker](https://docs.docker.com/)
- [GCP Secret Manager](https://cloud.google.com/secret-manager)
- [SendGrid](https://sendgrid.com/docs/)

