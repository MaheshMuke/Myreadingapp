# Drift — PDF Reader

Drift is a phone-friendly installable web app for reading PDF books. It renders PDF pages for high-fidelity layout, with a selectable text layer for word lookup, continuous automatic scrolling, saved reading position and preferences, four reading themes, focus mode, font controls, scanned-page OCR, and a screen-orientation control. Optional ambient instrumental audio is synthesized locally.

## Run it on Android

1. Put `index.html`, `manifest.webmanifest`, `sw.js`, and `icon.svg` on a static web host that serves HTTPS (for example, GitHub Pages or a personal web host). Browser security requires HTTPS for installation and orientation controls.
2. Open the hosted `index.html` in Chrome on your Android phone.
3. Choose **Add to Home screen** from Chrome’s menu. Open Drift from the new home-screen icon.
4. Use **Choose a PDF**. Your book and progress are stored in that browser on that phone.

You can also preview it on a computer by opening `index.html`, though PDF.js and OCR/dictionary services load from the internet.

## Features and notes

- PDF pages are rendered as pages to preserve their original layout. Selectable text overlays retain word lookup; extracted text is saved in a structured, reflowed form for the saved-book view.
- Pages with little or no extractable text are identified for OCR. Choose **Settings → Run OCR** to recognize them. The first run downloads the English Tesseract.js engine from jsDelivr and therefore needs internet access; progress is reported page by page. Download or initialization errors include details and can be retried. Recognized text remains selectable and is saved locally.
- Select a word in the reading text to look up its English definition. Dictionary lookup needs an internet connection.
- Choose **Focus** to hide the whole app interface. Tap the reading area to reveal a temporary **Exit focus** control. Reading position, theme, font, scroll speed, and audio volume are saved automatically in local browser storage. Clearing browser data removes the saved book and preferences.
- Scrolling speed is adjustable from 5 to 120 pixels per second and can be changed while auto-scroll is active.
- Optional **Settings → Reading music** generates a quiet ambient instrumental soundscape with the Web Audio API; no music files or copyrighted recordings are bundled or downloaded. Playback is off by default and depends on browser audio support and device playback settings.
- Auto-scroll pauses at the end of the book. The Rotate button requests landscape orientation where Android/browser support permits it; the device may require the app to be installed and in full-screen mode.

PDF.js and the OCR engine load from public CDNs. Music is generated locally; no audio files need to be supplied. This app does not upload books to a server.
