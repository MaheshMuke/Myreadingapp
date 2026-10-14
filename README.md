# Drift — PDF Reader

Drift is a phone-friendly installable web app for reading PDF books. It renders PDF pages for high-fidelity layout, with a selectable text layer for word lookup, continuous automatic scrolling, saved reading position and preferences, four reading themes, focus mode, font controls, scanned-page OCR, and a screen-orientation control. Optional ambient instrumental audio is synthesized locally.

## Run it on Android

1. Put `index.html`, `manifest.webmanifest`, `sw.js`, and `icon.svg` on a static web host that serves HTTPS (for example, GitHub Pages or a personal web host). Browser security requires HTTPS for installation and orientation controls.
2. Open the hosted `index.html` in Chrome on your Android phone.
3. Choose **Add to Home screen** from Chrome’s menu. Open Drift from the new home-screen icon.
4. Use **Choose a PDF** to import a book. It appears under **My Books**, where you can continue from your saved place, open it from the beginning, or remove it.

You can also preview it on a computer by opening `index.html`, though PDF.js and OCR/dictionary services load from the internet.

## Features and notes

- PDFs, extracted page text, and reading positions are stored locally in the browser's IndexedDB library. No book is uploaded. Library storage uses device/browser quota; if storage is unavailable or full, Drift reports that the import could not be saved. Removing a book also removes its saved progress. Clearing browser data removes the local library.
- PDF pages are rendered as pages to preserve their original layout. Selectable text overlays retain word lookup, and reopening a library book loads its saved PDF without asking you to select the source file again.
- Pages with little or no extractable text are identified for OCR. Choose **Settings → Run OCR** to recognize them. The first run downloads the English Tesseract.js engine from jsDelivr and therefore needs internet access; progress is reported page by page. Download or initialization errors include details and can be retried. Recognized text remains selectable and is saved locally.
- Select a word in the reading text to look up its English definition. Dictionary lookup needs an internet connection.
- Choose **Focus** to hide the whole app interface. Tap the reading area to reveal a temporary **Exit focus** control. Auto-scroll pauses when the app is backgrounded or loses focus, saves the current page and offset, and stays paused until you press **Resume**. Reading preferences are saved in local browser storage.
- Scrolling speed is adjustable from 5 to 120 pixels per second and can be changed while auto-scroll is active.
- Optional **Settings → Reading music** generates ambient tones, soft piano, or gentle chimes with the Web Audio API; no music files or copyrighted recordings are bundled or downloaded. Playback is off by default and depends on browser audio support and device playback settings.
- Auto-scroll pauses at the end of the book. The responsive layout uses phone viewport and safe-area insets; the installed PWA requests standalone display. The Rotate button requests landscape orientation where Android/browser support permits it; the device may require the app to be installed and in full-screen mode.

PDF.js and the OCR engine load from public CDNs. Music is generated locally; no audio files need to be supplied. This app does not upload books to a server.
