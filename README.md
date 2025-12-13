<div align="center">

# 🥑 MacroMate

### *Your AI-Powered Nutrition Companion*

[![Flutter](https://img.shields.io/badge/Flutter-3.0+-02569B?logo=flutter&logoColor=white)](https://flutter.dev)
[![Firebase](https://img.shields.io/badge/Firebase-Enabled-FFCA28?logo=firebase&logoColor=black)](https://firebase.google.com)
[![Gemini AI](https://img.shields.io/badge/Gemini-AI%20Powered-4285F4?logo=google&logoColor=white)](https://ai.google.dev)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Android%20%7C%20iOS%20%7C%20Web%20%7C%20macOS%20%7C%20Linux-blue)](https://flutter.dev)

**MacroMate** is a premium, AI-powered macro tracking application that revolutionizes the way you monitor nutrition, weight, and daily habits. Built with Flutter and powered by Google Gemini AI, it offers a sleek, modern dark-mode interface with intelligent food logging capabilities.

[Features](#-features) • [Demo](#-demo) • [Installation](#-installation--setup) • [Configuration](#-configuration)

</div>


---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🎬 Demo](#-demo)
- [🔧 Prerequisites](#-prerequisites)
- [⚡ Installation & Setup](#-installation--setup)
- [🔑 Configuration](#-configuration)
  - [Firebase Database Setup](#1-firebase-database-setup)
  - [Google Gemini AI Setup](#2-google-gemini-ai-setup)
  - [Alternative: ChatGPT API](#alternative-chatgpt-api-integration)
- [🚀 Running the Application](#-running-the-application)
- [📱 Building for Release](#-building-for-release)
- [🏗️ Project Structure](#️-project-structure)
- [🛠️ Tech Stack](#️-tech-stack)
- [❓ Troubleshooting](#-troubleshooting)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

---

## ✨ Features

### 🤖 AI-Powered Features
- **🍔 AI Food Logging**: Simply snap a photo or type a description (e.g., "Oatmeal with blueberries") and get instant macro analysis using Google Gemini AI
- **💬 AI Nutrition Coach**: Chat with your personal AI nutritionist for personalized advice, meal suggestions, and dietary guidance
- **🧠 AI Diet Strategy**: Get AI-generated meal strategies and recommendations based on your fitness goals

### 📊 Tracking & Analytics
- **📈 Smart Dashboard**: Real-time tracking of Calories, Protein, Carbs, and Fat against your personalized TDEE targets
- **⚖️ Weight Tracker**: Log your weight daily and visualize trends over time with beautiful interactive charts
- **💧 Habit Tracking**: Track daily water intake with quick-add buttons and visual progress indicators
- **📉 Trends & Insights**: Analyze your nutrition patterns with detailed charts powered by fl_chart

### 🍽️ Meal Planning & Recipes
- **🗓️ Weekly Meal Planner**: Plan your entire week with organized meals (Breakfast, Lunch, Dinner, Snacks)
- **🍳 Recipe Builder**: Create and save custom recipes with ingredient tracking
- **📚 Recipe Library**: Browse and manage your collection of favorite recipes
- **📸 Barcode Scanner**: Quickly log packaged foods by scanning barcodes (Mobile only)

### 🎨 Premium Design
- **🌙 Dark Mode Interface**: Beautiful, modern dark-themed UI designed for extended use
- **🎯 Intuitive UX**: Smooth animations and responsive design across all platforms
- **📱 Cross-Platform**: Seamlessly works on Windows, Android, iOS, Web, macOS, and Linux
- **🔐 Secure Authentication**: Firebase-powered login with email/password and Google Sign-In

---

## 🎬 Demo

### Application Walkthrough
[🔗Demo Video if below video not play](https://github.com/kamlesh-IY9/MacroMate-AI-V.0.3/blob/e1f7691448358c12c93e847735a241bce99c8584/MacroMate_AI_Demo_Video.mp4)

https://github.com/user-attachments/assets/dc18a20e-fdf0-416f-bcfe-a8bfec226f51


*Main dashboard, AI food logging, and tracking features*

*Firebase data storage and cloud sync*

> **Note**: Demo videos showcase the application's key features including AI-powered food logging, real-time macro tracking, weight trends, meal planning, recipe management, and the AI nutrition coach.

---

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

### Required Software
- **Flutter SDK** (version 3.0.0 or higher)
  - [Download Flutter](https://flutter.dev/docs/get-started/install)
  - Verify installation: `flutter --version`
  
- **Dart SDK** (comes with Flutter)

- **Git** (for cloning the repository)
  - [Download Git](https://git-scm.com/downloads)

### Platform-Specific Requirements

| Platform | Requirements |
|----------|-------------|
| **Windows** | Windows 10/11, Visual Studio 2022 with C++ tools |
| **Android** | Android Studio, Android SDK (API 21+) |
| **iOS** | macOS, Xcode 14+, CocoaPods |
| **macOS** | macOS 10.14+, Xcode 14+ |
| **Linux** | Linux development packages, GTK 3.0+ |
| **Web** | Chrome browser (for testing) |

### Required Accounts
- **Firebase Account** (free tier available)
  - [Create Firebase Account](https://console.firebase.google.com)
  
- **Google AI Studio Account** (for Gemini API)
  - [Get Gemini API Key](https://aistudio.google.com/)

---

## ⚡ Installation & Setup

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone https://github.com/yourusername/macro_tracker_ai.git

# Navigate to project directory
cd macro_tracker_ai
```

### Step 2: Install Dependencies

```bash
# Install Flutter packages
flutter pub get

# Run code generation for Riverpod and JSON serialization
flutter pub run build_runner build --delete-conflicting-outputs
```

### Step 3: Verify Flutter Installation

```bash
# Check for any issues
flutter doctor

# List available devices
flutter devices
```

> **Tip**: If `flutter doctor` shows any issues, follow the suggested fixes before proceeding.

---

## 🔑 Configuration

MacroMate requires two main configurations: Firebase for data storage and Google Gemini AI for intelligent food logging.

### 1. Firebase Database Setup

Firebase is used for user authentication and storing all user data.

#### A. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create a new project (e.g., "MacroMate-AI")
3. Enable **Authentication** (Email/Password and Google Sign-In)
4. Enable **Cloud Firestore**

#### B. Set up Cloud Firestore

1. In Firebase Console, go to **Firestore Database**
2. Click **"Create database"**
3. Select **Production mode** or **Test mode** (for development)
4. Choose a Cloud Firestore location
5. Update Firestore security rules (example for development):

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

#### C. Configure Your App

**For Web:**
1. In Firebase Console, go to **Project Settings** → **Your apps**
2. Click the Web icon `</>`
3. Register your app (nickname: "MacroMate Web")
4. Copy the Firebase config
5. Update `web/index.html` with your credentials

**For Android:**
1. Add an Android app in Firebase Console
2. Enter package name: `com.example.macro_tracker_ai`
3. Download `google-services.json`
4. Place in `android/app/` folder

**For iOS:**
1. Add an iOS app in Firebase Console
2. Enter bundle ID: `com.example.macroTrackerAi`
3. Download `GoogleService-Info.plist`
4. Place in `ios/Runner/` folder

---

### 2. Google Gemini AI Setup

The AI food logging and nutrition coach features require a Google Gemini API key.

#### A. Get Your API Key

1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Sign in with your Google account
3. Click **"Get API Key"** in the top navigation
4. Click **"Create API key"**
5. Select your Google Cloud project (or create a new one)
6. Copy the generated API key

#### B. Configure in MacroMate

**Option 1: Configure in App (Recommended)**
1. Launch MacroMate
2. Navigate to **Settings** page (bottom navigation)
3. Scroll to **AI Provider** section
4. Select **"Google Gemini"**
5. Paste your API key
6. Click **"Save"**
7. API key is securely stored locally on your device

**Option 2: Environment Variables (Advanced)**
```bash
# Windows PowerShell
$env:GEMINI_API_KEY="your-api-key-here"
flutter run

# macOS/Linux
export GEMINI_API_KEY="your-api-key-here"
flutter run
```

> **Security Note**: Never commit API keys to version control. They are stored locally using `shared_preferences` and never transmitted except to Google AI services.

#### C. Verify AI Features

1. Go to the **Dashboard** or **Logging** screen
2. Click **"Add Food"** → **"AI Analysis"**
3. Type a food description or take a photo
4. If configured correctly, you'll see macro analysis results

---

### Alternative: ChatGPT API Integration

MacroMate also supports ChatGPT as an alternative AI provider.

#### A. Get OpenAI API Key

1. Visit [OpenAI Platform](https://platform.openai.com/api-keys)
2. Sign in or create an account
3. Navigate to **API Keys** section
4. Click **"Create new secret key"**
5. Copy the generated key

#### B. Configure in MacroMate

1. Launch MacroMate
2. Go to **Settings** → **AI Provider**
3. Select **"ChatGPT"**
4. Paste your OpenAI API key
5. Choose your preferred model (e.g., GPT-4, GPT-4o)
6. Click **"Save"**

**Available Models:**
- `gpt-4o` - Latest multimodal model (recommended)
- `gpt-4-turbo` - Fast and cost-effective
- `gpt-3.5-turbo` - Budget-friendly option

> **Note**: ChatGPT API usage is billed by OpenAI. Check their pricing at [openai.com/pricing](https://openai.com/pricing)

---

## 🚀 Running the Application

### Run on Specific Platform

Once configuration is complete, you can run MacroMate on any platform:

```bash
# Windows
flutter run -d windows

# Android (with device/emulator connected)
flutter run -d android

# iOS (macOS only, with simulator/device)
flutter run -d ios

# Web
flutter run -d chrome

# macOS
flutter run -d macos

# Linux
flutter run -d linux
```

### Select Device Interactively

```bash
# List all available devices
flutter devices

# Run and select device
flutter run
```

### Hot Reload During Development

While the app is running:
- Press `r` to hot reload
- Press `R` to hot restart
- Press `q` to quit

---

## 📱 Building for Release

### Android APK/Bundle

```bash
# Build APK (for direct installation)
flutter build apk --release

# Output: build/app/outputs/flutter-apk/app-release.apk

# Build App Bundle (for Play Store)
flutter build appbundle --release
```

### iOS

```bash
# Build for iOS (requires macOS)
flutter build ios --release

# Open in Xcode for signing and distribution
open ios/Runner.xcworkspace
```

### Windows Executable

```bash
# Build Windows executable
flutter build windows --release

# Output: build\windows\runner\Release\
```

### Web

```bash
# Build for web deployment
flutter build web --release

# Output: build/web/
```

### macOS

```bash
# Build for macOS
flutter build macos --release
```

---

## 🏗️ Project Structure

```
macro_tracker_ai/
├── lib/
│   ├── core/              # Core utilities and theme
│   ├── features/          # Feature modules
│   │   ├── auth/         # Authentication screens
│   │   ├── dashboard/    # Main dashboard
│   │   ├── logging/      # Food logging and AI analysis
│   │   ├── food_search/  # Food database search
│   │   ├── meal_planner/ # Meal planning
│   │   ├── recipes/      # Recipe builder & library
│   │   ├── weight/       # Weight tracking
│   │   ├── trends/       # Charts and analytics
│   │   ├── nutrition/    # Nutrition insights
│   │   ├── coach/        # AI nutrition coach
│   │   ├── strategy/     # Diet strategy planner
│   │   ├── history/      # Food log history
│   │   └── settings/     # App settings
│   ├── models/           # Data models (Food, User, Meal, etc.)
│   ├── providers/        # Riverpod state providers
│   ├── services/         # API services
│   │   ├── ai_service.dart      # Google Gemini integration
│   │   ├── auth_service.dart    # Firebase authentication
│   │   ├── firestore_service.dart # Cloud Firestore
│   │   ├── food_log_service.dart  # Food logging
│   │   ├── meal_planner_service.dart
│   │   ├── recipe_service.dart
│   │   ├── user_service.dart
│   │   ├── weight_service.dart
│   │   └── water_service.dart
│   └── main.dart         # App entry point
├── android/              # Android-specific code
├── ios/                  # iOS-specific code
├── windows/              # Windows-specific code
├── web/                  # Web-specific code
├── macos/                # macOS-specific code
├── linux/                # Linux-specific code
├── assets/               # Images and resources
│   └── app_icon.png     # App icon
└── pubspec.yaml          # Dependencies
```

### Key Files

| File | Purpose |
|------|---------|
| `lib/main.dart` | Application entry point, Firebase initialization |
| `lib/services/ai_service.dart` | Google Gemini AI integration with HTTP fallback |
| `lib/services/auth_service.dart` | Firebase Authentication (Email + Google Sign-In) |
| `lib/services/firestore_service.dart` | Cloud Firestore operations |
| `lib/providers/` | Riverpod state management |
| `lib/models/` | Data models with JSON serialization |

---

## 🛠️ Tech Stack

![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)
![Firebase](https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-%238E75B2.svg?style=for-the-badge&logo=google&logoColor=white)
![Riverpod](https://img.shields.io/badge/Riverpod-%232D3440.svg?style=for-the-badge&logo=flutter&logoColor=white)
![Android Studio](https://img.shields.io/badge/Android%20Studio-3DDC84.svg?style=for-the-badge&logo=android-studio&logoColor=white)

### Core Framework
- **[Flutter](https://flutter.dev)** `^3.0.0` - Cross-platform UI framework
- **[Dart](https://dart.dev)** `^3.0.0` - Programming language

### State Management
- **[flutter_riverpod](https://pub.dev/packages/flutter_riverpod)** `^2.5.1` - Reactive state management
- **[riverpod_annotation](https://pub.dev/packages/riverpod_annotation)** `^2.3.5` - Code generation for Riverpod
- **[state_notifier](https://pub.dev/packages/state_notifier)** `^1.0.0` - State change notifier

### Backend & Database
- **[firebase_core](https://pub.dev/packages/firebase_core)** `^3.1.0` - Firebase initialization
- **[firebase_auth](https://pub.dev/packages/firebase_auth)** `^5.1.0` - User authentication
- **[cloud_firestore](https://pub.dev/packages/cloud_firestore)** `^5.0.0` - NoSQL cloud database
- **[google_sign_in](https://pub.dev/packages/google_sign_in)** `^6.2.1` - Google OAuth integration

### AI & Machine Learning
- **Google Gemini API** (HTTP fallback) - Vision and text analysis for food recognition
- **ChatGPT API Support** - Alternative AI provider for food analysis and coaching

### Navigation
- **[go_router](https://pub.dev/packages/go_router)** `^14.0.0` - Declarative routing

### UI & Visualization
- **[fl_chart](https://pub.dev/packages/fl_chart)** `^0.68.0` - Interactive charts and graphs
- **[cupertino_icons](https://pub.dev/packages/cupertino_icons)** `^1.0.6` - iOS-style icons

### Utilities
- **[shared_preferences](https://pub.dev/packages/shared_preferences)** `^2.2.3` - Local data persistence
- **[image_picker](https://pub.dev/packages/image_picker)** `^1.0.7` - Camera/gallery access
- **[image_picker_windows](https://pub.dev/packages/image_picker_windows)** `^0.2.2` - Windows image picker support
- **[mobile_scanner](https://pub.dev/packages/mobile_scanner)** `^5.1.0` - Barcode scanning
- **[openfoodfacts](https://pub.dev/packages/openfoodfacts)** `^3.1.0` - Food database API
- **[http](https://pub.dev/packages/http)** `^1.1.0` - HTTP requests
- **[intl](https://pub.dev/packages/intl)** `^0.19.0` - Internationalization
- **[uuid](https://pub.dev/packages/uuid)** `^4.4.0` - Unique ID generation
- **[json_annotation](https://pub.dev/packages/json_annotation)** `^4.9.0` - JSON serialization annotations

### Development Tools
- **[build_runner](https://pub.dev/packages/build_runner)** `^2.4.9` - Code generation
- **[riverpod_generator](https://pub.dev/packages/riverpod_generator)** `^2.4.0` - Riverpod code generation
- **[freezed](https://pub.dev/packages/freezed)** `^2.5.2` - Immutable data classes
- **[json_serializable](https://pub.dev/packages/json_serializable)** `^6.8.0` - JSON serialization
- **[flutter_launcher_icons](https://pub.dev/packages/flutter_launcher_icons)** `^0.13.1` - App icon generation

---

## ❓ Troubleshooting

### Common Issues

<details>
<summary><b>🔴 Build failed: "Plugin not found"</b></summary>

**Solution:**
```bash
# Clean Flutter
flutter clean

# Remove existing symlinks (Windows only)
Remove-Item -Recurse -Force windows/flutter/ephemeral

# Reinstall dependencies
flutter pub get

# Rebuild
flutter run
```

</details>

<details>
<summary><b>🔴 Firebase not initialized</b></summary>

**Error**: `[core/no-app] No Firebase App '[DEFAULT]' has been created`

**Solution:**
1. Verify Firebase configuration files exist:
   - Web: Check `web/index.html` has Firebase config
   - Android: `android/app/google-services.json`
   - iOS: `ios/Runner/GoogleService-Info.plist`
2. Check that `Firebase.initializeApp()` is called in `main.dart`
3. Run `flutter clean` and rebuild

</details>

<details>
<summary><b>🔴 Gemini API not working</b></summary>

**Symptoms**: AI food analysis returns errors or nothing happens

**Solutions:**
1. Verify API key is correct in Settings
2. Check API key is enabled in Google Cloud Console
3. Ensure you haven't exceeded free tier quota (60 requests/minute)
4. Test API key: [Gemini API Docs](https://ai.google.dev/tutorials/rest_quickstart)
5. Try switching to ChatGPT as alternative AI provider

</details>

<details>
<summary><b>🔴 ChatGPT API not working</b></summary>

**Solutions:**
1. Verify OpenAI API key is correct
2. Check your account has credits/billing enabled
3. Ensure selected model is available (try `gpt-3.5-turbo`)
4. Check for rate limit errors in logs

</details>

<details>
<summary><b>🔴 Charts not displaying</b></summary>

**Solution:**
1. Ensure you have data logged (weight, meals)
2. Try pulling down to refresh
3. Check date range filters
4. Restart the app

</details>

<details>
<summary><b>🔴 Barcode scanner not working</b></summary>

**Solution:**
1. Grant camera permissions in device settings
2. Barcode scanner only works on mobile (Android/iOS)
3. Ensure `mobile_scanner` plugin is properly installed

</details>

<details>
<summary><b>🔴 Windows build issues</b></summary>

**Error**: C++ build tools not found or CMake errors

**Solution:**
1. Install Visual Studio 2022 with "Desktop development with C++"
2. Ensure CMake is installed and accessible
3. Run `flutter doctor` to verify
4. Restart terminal/IDE after installation
5. Try `flutter clean` and rebuild

</details>

<details>
<summary><b>🔴 Google Sign-In not working</b></summary>

**Solution:**
1. Ensure `google_sign_in` is configured in Firebase Console
2. For Android: Check SHA-1 fingerprint is added to Firebase
3. For iOS: Check URL schemes are configured in Xcode
4. Verify Google Sign-In is enabled in Firebase Authentication

</details>

### Getting Help

If you encounter other issues:

1. **Check Flutter Doctor**: Run `flutter doctor -v` for diagnostic info
2. **Review logs**: Use `flutter run --verbose` for detailed output
3. **Search issues**: Check [GitHub Issues](https://github.com/yourusername/macro_tracker_ai/issues)
4. **Ask for help**: Open a new issue with:
   - Flutter version (`flutter --version`)
   - Platform (Windows, Android, etc.)
   - Error logs
   - Steps to reproduce

---

## 🤝 Contributing

Contributions are welcome!
- This project is a comprehensive example of building a production-grade **Flutter AI application** using **Clean Architecture**, **Riverpod**, and **Google Gemini** for image recognition and natural language processing.
---

## 📄 License

This project is licensed under the **MIT License**.

<div align="center">

### Made with ❤️ using Flutter

**MacroMate** - *Transform your nutrition journey with AI*

[⬆ Back to Top](#-macromate)

</div>
