# FuelTrack V5 — Barcode Scanner

Compatible with the existing FuelTrack public GitHub Pages repository and previous locally stored diary entries (localStorage key `fueltrack-v2`).

## Publishing

1. Open FuelTrack and export a backup from Settings.
2. Replace the root `index.html` and `sw.js` in your existing GitHub repository with these V5 files. The manifest and icons can remain unchanged.
3. After GitHub Pages deploys, fully close and reopen the installed Pixel 8a app. If V4 remains, refresh the browser site and reopen the app; service-worker updates can take another launch.

## Barcode scanning

Tap Scan barcode on Today or Diary, allow camera access, and point at the barcode. The Pixel 8a uses native BarcodeDetector when supported. For other browsers the app tries to load html5-qrcode from jsDelivr on demand (internet required). There is always manual code entry.

Products are fetched from Open Food Facts (a community-run database). Lookups need internet; diary entries and previously saved personal foods remain local/offline. Missing nutrition is left at zero when loaded and must be corrected from the label before saving; the UI indicates missing fields. Data is provided under Open Food Facts licensing terms and may be incomplete.

The scanner has not been physically tested on the user's phone. Camera permission and device/browser support are required.
