# Serverpod Admin Portal Shared

This package contains shared custom models for the Serverpod Admin Portal monorepo. Use this for models that need to be serialized and shared between the server, client, and Flutter app.

---

## ✨ Features
- Shared Dart models for server, client, and Flutter app
- Serverpod serialization support
- Central place for protocol definitions (see `lib/protocol/`)

---

## 🚀 Getting Started

1. Add this package as a path dependency in your `pubspec.yaml`:
   ```yaml
   dependencies:
     serverpod_admin_portal_shared:
       path: ../serverpod_admin_portal_shared
   ```
2. Run `dart pub get` or `flutter pub get` in your project.
3. Import and use shared models:
   ```dart
   import 'package:serverpod_admin_portal_shared/protocol/user_info.dart';
   ```

---

## 📝 Usage Example

```dart
import 'package:serverpod_admin_portal_shared/protocol/user_info.dart';

final user = UserInfo(id: 1, name: 'Alice', email: 'alice@example.com');
final json = user.toJson();
final userFromJson = UserInfo.fromJson(json);
```

---

## 📂 Structure
- `lib/protocol/` – Place your shared models here
- `lib/protocol.yaml` – List models for Serverpod code generation

---

## 🤝 Contributing
- Add new models to `lib/protocol/`
- Update `protocol.yaml` for code generation
- Use path dependencies in server, client, and Flutter app

---

## 📚 References
- [Serverpod Serialization](https://docs.serverpod.dev/concepts/serialization)
- [Dart Packages](https://dart.dev/guides/libraries/create-packages)
