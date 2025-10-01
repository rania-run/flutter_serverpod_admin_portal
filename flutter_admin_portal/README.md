# Flutter Admin Portal

This is the **Flutter web app** for the Admin Portal, built with Flutter 3.35.4 and managed via [Puro](https://puro.dev/). It is designed to consume Serverpod APIs, but can also integrate with other protocols and services (REST, GraphQL, gRPC, Firebase, etc.).

---

## ✨ Features
- Modern Flutter web UI for admin operations
- Supports multiple backend protocols: Serverpod, REST, GraphQL, gRPC, Firebase, and more
- Clean, feature-first architecture (domain/data/presentation)
- Secure authentication and session management
- Responsive theming and localization

---

## 🛠 Requirements
- Flutter 3.35.4 (Puro managed)
- Dart 3.7+
- Web target enabled
- Access to your chosen backend(s) (Serverpod, Firebase, etc.)

---

## 🚀 Getting Started

### 1. Install dependencies
```bash
puro flutter pub get
```

### 2. Run local flavor
```bash
puro flutter run -t lib/main_local.dart
```

### 3. Build for web (staging example)
```bash
puro flutter build web -t lib/main_stg.dart --dart-define=API_URL=https://stg-api.example.com
```

---

## ⚙️ Configuration
- API endpoints and backend integrations are configured via `dart-define` or environment files
- For Serverpod, set `API_URL` to your backend endpoint
- For Firebase, configure via `firebase_options.dart` and `google-services.json`/`GoogleService-Info.plist`
- For REST/GraphQL/gRPC, update the relevant data sources in your repository

---

## 📂 Project Structure
- `lib/` – Main Flutter app code
  - `core/` – Theming, localization, utilities
  - `features/` – Feature-first modules (domain/data/presentation)
  - `data/` – Data sources (Serverpod, REST, GraphQL, Firebase, etc.)
  - `main.dart` / `main_local.dart` / `main_stg.dart` – App entry points for different flavors
- `web/` – Web-specific files
- `test/` – Unit and widget tests

---

## 🎨 Project Conventions
- **Architecture**: Clean, feature-first (domain/data/presentation)
- **State Management**: Riverpod + Freezed (Bloc optional for interop)
- **Theming**: Centralized in `core/theme/` (`AppColors`, `AppTextStyles`)
- **Localization**: ARB files (`en`, `sv`) → `flutter gen-l10n`

---

## 📦 Dependencies
- `flutter_riverpod`
- `freezed`
- `http`, `dio`, `graphql`, `grpc` (pluggable networking)
- `firebase_core`, `firebase_auth` (if using Firebase)
- `logger` (logging abstraction)

---

## 🧪 Testing
- To run tests:
```bash
puro flutter test
```
- Add your tests in the `test/` directory

---

## 🛠 Troubleshooting
- Ensure the correct backend endpoints are set via `dart-define` or config files
- For build issues, run `puro flutter clean` and `puro flutter pub get`
- For network/auth issues, check backend availability and credentials
- For more help, see [Flutter Documentation](https://docs.flutter.dev/) and your backend's docs

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
