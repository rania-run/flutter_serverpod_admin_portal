# Flutter + Serverpod Admin Portal (Monorepo)

This is a **monorepo template** for building **Flutter web admin dashboards** with a **Serverpod backend**. It’s designed for **clean architecture**, **multi-flavor environments (local/dev/stg/prod)**, theming (light/dark/system), localization (EN/SV), and flexible networking (REST/GraphQL/gRPC/Firebase).

---

## ✨ Features
- Modern Flutter web admin dashboard
- Serverpod backend with endpoints, DB, migrations, and integrations
- Multi-flavor support: local, development, staging, production
- Flexible networking: Serverpod, REST, GraphQL, gRPC, Firebase
- Clean, feature-first architecture (domain/data/presentation)
- Theming (light/dark/system) and localization (EN/SV)
- Role-based authentication and permissions
- CI/CD ready (Cloud Build → Cloud Run)

---

## 📂 Project Structure

```
flutter_serverpod_admin_portal/
├── flutter_admin_portal/                 # Flutter web app (Puro-managed, Flutter 3.35.4)
│   └── .puro/                            # Puro SDK files (created by Puro)
│
└── serverpod_admin_portal/               # Serverpod backend workspace
    ├── serverpod_admin_portal_client/    # Generated Dart client (consumed by Flutter)
    ├── serverpod_admin_portal_flutter/   # Flutter helpers for Serverpod (not a full app)
    └── serverpod_admin_portal_server/    # Backend server (endpoints, DB, migrations)
```

---

## 🛠 Requirements
- [Flutter 3.35.4](https://docs.flutter.dev/get-started/install) (managed with [Puro](https://puro.dev/))
- Dart SDK (bundled with Flutter or system-wide)
- Docker (for Postgres in local dev)
- Serverpod CLI
  ```bash
  dart pub global activate serverpod_cli
  ```

---

## 🚀 Getting Started

### 1. Run Serverpod locally
```bash
cd serverpod_admin_portal/serverpod_admin_portal_server

dart bin/main.dart --apply-migrations   # Apply migrations
dart bin/main.dart                      # Start server
```
➡️ Backend runs on [http://localhost:8080](http://localhost:8080)

---

### 2. Run Flutter app
```bash
cd flutter_admin_portal

puro flutter pub get                    # Install dependencies
puro flutter run -t lib/main_local.dart # Run local flavor
```

---

## 🌐 Flavors & Environments
- `local` → Connects to `http://localhost:8080`
- `development` → Cloud Run dev deployment
- `staging` → Cloud Run staging deployment
- `production` → Cloud Run production deployment
- Use `--dart-define=API_URL=...` to override endpoints

---

## ⚙️ Configuration
- API endpoints and backend integrations are configured via `dart-define` or environment files
- For Serverpod, set `API_URL` to your backend endpoint
- For Firebase, configure via `firebase_options.dart` and `google-services.json`/`GoogleService-Info.plist`
- For REST/GraphQL/gRPC, update the relevant data sources in your repository

---

## 🎨 Conventions & Architecture
- **Architecture**: Clean, feature-first (domain/data/presentation)
- **State Management**: Riverpod + Freezed (Bloc optional for interop)
- **Theming**: Centralized in `core/theme/` (`AppColors`, `AppTextStyles`)
- **Localization**: ARB files (`en`, `sv`) → `flutter gen-l10n`

---

## 📦 Dependencies
### Flutter
- `flutter_riverpod`, `freezed`, `flutter_bloc` (optional)
- `http`, `dio`, `graphql`, `grpc` (pluggable networking)
- `firebase_core`, `firebase_auth` (if using Firebase)
- `logger` (logging abstraction)
### Serverpod
- Auth & role/scope-based permissions
- DB migrations (Postgres)
- SendGrid email integration
- GCP (Storage + Secret Manager)
- Notifications (WebSocket, streams)

---

## 🧪 Testing
- To run Flutter tests:
```bash
cd flutter_admin_portal
puro flutter test
```
- To run Serverpod tests:
```bash
cd serverpod_admin_portal/serverpod_admin_portal_server
dart test
```

---

## 🛠 Troubleshooting
- Ensure Docker is running for local Postgres/Redis
- Check that all environment variables are set
- For migration issues, verify your YAML model definitions
- For build issues, run `puro flutter clean` and `puro flutter pub get`
- For more help, see [Serverpod Documentation](https://docs.serverpod.dev/) and [Flutter Documentation](https://docs.flutter.dev/)

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License
[MIT](LICENSE)

---

## 📚 References
- [Flutter Documentation](https://docs.flutter.dev/)
- [Serverpod Documentation](https://docs.serverpod.dev/)
- [Firebase Documentation](https://firebase.google.com/docs)
- [Dart Language](https://dart.dev/)
- [Puro](https://puro.dev/)

---

## 📝 Next Steps
1. Add **linting, theming, and logging** to Flutter app (`flutter_admin_portal`).
2. Create **first endpoint** in Serverpod (`auth_endpoint.dart`) for login/logout.
3. Wire **Flutter app** to call `auth_endpoint` via generated client.
4. Setup **CI/CD** (Cloud Build → Cloud Run) with flavors (dev/stg/prod).
