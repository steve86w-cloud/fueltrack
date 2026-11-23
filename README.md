# FuelTrack — iPhone + Android PWA

FuelTrack is a local-first demonstration app, not an App Store or Play Store application.

## Free deployment (GitHub Pages)
1. Create a public GitHub repository named `fueltrack` (or any name).
2. Upload **all the contents** of this folder, preserving `icons/` (not the enclosing folder).
3. In repository **Settings → Pages**, choose **Deploy from a branch**, `main`, `/ (root)` and Save.
4. Open the HTTPS URL GitHub provides, typically `https://YOUR_USERNAME.github.io/fueltrack/`.
5. iPhone 13 Pro: open that URL in **Safari → Share → Add to Home Screen → Add**.
6. Pixel 8a: open it in **Chrome → ⋮ → Install app** (or Add to Home screen).

## Important notes
- Data is stored locally in browser storage. Data does NOT synchronise between phones.
- Use **Settings → Export backup** regularly; clear-site-data, uninstalling, or browser cleanup may delete entries.
- Offline app files are cached after a successful hosted visit. Test by installing, opening once online, then switching to airplane mode.
- Barcode scanning, camera AI, cloud sync and live food databases are NOT implemented in this build.
- `index.html` opened from Files is a preview only: service workers and installability require HTTPS or localhost.
- Food nutrition values are estimates, not medical advice.

Files: `index.html`, `manifest.webmanifest`, `sw.js`, `icons/*`.
