# Build Drift for Android

This Android Studio project wraps the reader in a small native Android app. Imported PDFs, cached rendered pages, extracted/OCR reading data, library details, and exact saved reading positions stay in the app's local WebView storage; no book is uploaded. Reopening a saved book reuses its cached pages and text instead of rendering or extracting them again. Use **My Books** to continue reading, open a saved PDF from the beginning, or remove it (which also deletes its saved data and progress). The reader page is maintained at `../index.html` and copied into `app/src/main/assets/index.html`.

## Build the APK

1. Install Android Studio on a computer and let its setup wizard install Android SDK Platform 35 and a compatible Android Gradle Plugin/Gradle runtime.
2. In Android Studio, choose **Open** and select this `android` folder.
3. Wait for Gradle sync, then choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
4. Android Studio will show **locate** when the APK is ready. Copy `app-debug.apk` to your phone, tap it, and allow **Install unknown apps** for the app used to open it if Android asks.

The project uses PDF.js from its public CDN. The first OCR run downloads the English Tesseract.js engine from jsDelivr; OCR reports per-page progress and can be retried if the engine cannot load. Word definitions need internet. Book storage is subject to available app/device storage; import failures are reported. Auto-scroll pauses on Android activity pause and remains paused until **Resume** is pressed. Focus mode hides all reader controls until the page is tapped, and scroll speed and themes are adjustable and saved.

Optional reading music offers ambient tones, soft piano, and gentle chimes generated on-device with the Web Audio API, and is off by default; no copyrighted or bundled audio is used. Playback depends on Android WebView audio support and device playback settings. For regular use, make a signed release APK in Android Studio's **Build → Generate Signed Bundle / APK** flow.
