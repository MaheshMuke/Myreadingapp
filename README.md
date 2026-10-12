# Drift — PDF Reader

Drift is a phone-friendly installable web app for reading PDF books. It offers automatic upward scrolling with four speeds, locally saved reading position, paper/sepia/night themes, focus mode, font controls, word definitions, scanned-page OCR, and a screen-orientation control.

## Run it on Android

1. Put the files in `outputs` on a static web host that serves HTTPS (for example, GitHub Pages or a personal web host). Browser security requires HTTPS for installation and orientation controls.
2. Open the hosted `index.html` in Chrome on your Android phone.
3. Choose **Add to Home screen** from Chrome’s menu. Open Drift from the new home-screen icon.
4. Use **Choose a PDF**. Your book and progress are stored in that browser on that phone.

You can also preview it on a computer by opening `index.html`, though PDF.js and OCR/dictionary services load from the internet.

## Features and notes

- PDF text extraction runs in the browser. Image-only/scanned books can be processed using **Settings → Run OCR**; the first run downloads the English OCR engine and may take a while on large books.
- Select a word in the reading text to look up its English definition. Dictionary lookup needs an internet connection.
- Position and preferences are saved automatically in local browser storage. Clearing browser data removes the saved library and place.
- Auto-scroll pauses at the end of the book. The Rotate button requests landscape orientation where Android/browser support permits it; the device may require the app to be installed and in full-screen mode.

This is a working installable web-app prototype rather than a signed APK. It does not upload books to a server.
