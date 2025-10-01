# Serverpod Admin Portal Flutter

This is the **Flutter client** for the Admin Portal, built with Serverpod. It provides the user interface and communicates with the Serverpod backend.

---

## ✨ Features
- Modern Flutter UI for admin operations
- Secure authentication and session management
- Integration with Serverpod backend
- Responsive design for web, desktop, and mobile

---

## 🛠 Requirements
- Flutter 3.10+
- Dart 3.7+
- Serverpod backend running (see server README)

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd serverpod_admin_portal_flutter
```

### 2. Install dependencies
```bash
flutter pub get
```

### 3. Configure environment
- Ensure the Serverpod backend is running and accessible
- Update API endpoint URLs in your code/config if needed

### 4. Run the app
```bash
flutter run
```

---

## ⚙️ Configuration
- API endpoints are configured in the generated client or via environment files
- For web, update `web/index.html` if you need to set base URLs
- For mobile/desktop, check the initialization code in `main.dart`

---

## 📂 Project Structure
- `lib/` – Main Flutter app code
- `lib/main.dart` – App entry point
- `lib/generated/` – Generated Serverpod client code
- `test/` – Unit and widget tests
- `web/` – Web-specific files

---

## 🧪 Testing
- To run tests:
```bash
flutter test
```
- Add your tests in the `test/` directory

---

## 🛠 Troubleshooting
- Ensure the backend server is running and reachable
- Check API endpoint URLs if you get connection errors
- Run `flutter clean` and `flutter pub get` if you encounter build issues
- For more help, see [Serverpod Documentation](https://docs.serverpod.dev/) and [Flutter Documentation](https://docs.flutter.dev/)

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License
[MIT](LICENSE)

---

## 📚 References
- [Serverpod Documentation](https://docs.serverpod.dev/)
- [Flutter Documentation](https://docs.flutter.dev/)
- [Dart Language](https://dart.dev/)
