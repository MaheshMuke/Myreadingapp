# Build Drift for Android

This Android Studio project wraps the reader in a small native Android app. PDF books are selected from the phone and the saved reading position stays in the app's local storage.

## Build the APK

1. Install Android Studio on a computer and let its setup wizard install Android SDK Platform 35 and a compatible Android Gradle Plugin/Gradle runtime.
2. In Android Studio, choose **Open** and select this `android` folder.
3. Wait for Gradle sync, then choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
4. Android Studio will show **locate** when the APK is ready. Copy `app-debug.apk` to your phone, tap it, and allow **Install unknown apps** for the app used to open it if Android asks.

The project uses PDF.js from its public CDN, and OCR and word definitions also need internet. Your selected book and progress stay on the phone. For regular use, make a signed release APK in Android Studio's **Build → Generate Signed Bundle / APK** flow.
