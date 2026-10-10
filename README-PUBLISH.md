# BATIK ASM & BM 360 — Web App (PWA)

This folder is a Progressive Web App package for the BATIK ASM & BM 360 dashboard. It includes daily sales checkpoints, attendance, BM 360 scorecards, local history, JSON backup/import, and PNG report sharing/downloads.

## Publish free with GitHub Pages (no Android Studio required)

1. Sign in to GitHub and create a **new public repository** named `batik-asm-bm360` (do not add a README/license).
2. Extract this ZIP on your computer. Upload the *contents* of this folder to the repository root: `index.html`, `manifest.json`, `service-worker.js`, `icons/`, and this README.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then **Save**.
5. Wait for GitHub Pages to publish. The app URL will be `https://YOUR-GITHUB-USERNAME.github.io/batik-asm-bm360/`.
6. Open that URL on the Android phone in **Google Chrome**. Tap the three-dot menu → **Install app** (or **Add to Home screen**) → **Install**.

## Important
- The app needs HTTPS for installability; GitHub Pages supplies HTTPS.
- Records are saved locally in that browser on that phone. They are **not** sent to GitHub or synced to your laptop/other phones.
- Export a JSON backup regularly using the app's **Export all data** button. Clearing Chrome site data or uninstalling/resetting can erase local records.
- This is a single-user tool and does not connect to FootMetrics, Candela POS, WhatsApp Business APIs, or a shared database.
- GitHub repository source files will be publicly visible if you use a public repository; no sales data is included in the code package. Keep actual report data inside the app and do not commit backup JSON files.
- This package has been assembled but has not yet been deployed to a live URL or tested on your particular Android phone.
