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

## Updating an existing BATIK ASM & BM 360 deployment

For the existing `batik-asm-bm360` repository, do **not** create a second repository:

1. Extract this updated ZIP on your computer.
2. Open the existing GitHub repository and choose **Add file → Upload files**.
3. Upload/replace `index.html`, `service-worker.js`, `manifest.json`, and the three files inside `icons/`. Keep the folder structure intact. Do not upload JSON data backups.
4. Commit the changes to `main`.
5. Open **Settings → Pages** and confirm the source is `main` and `/(root)`.
6. Wait until the latest `github-pages` deployment shows a green tick. Then open the app and refresh it. If the old version remains, close all app tabs and reopen; the service-worker cache was bumped to v2 to request the new files.
7. Before entering real figures, export a JSON backup from the current app. The update uses the same local storage key, but keep a backup as a precaution.

## Changes in this quality-check build

- Sales report uses the latest non-blank cumulative checkpoint per branch (rather than adding all checkpoint snapshots together).
- Dashboard achievement displays one decimal place; the sales report includes an amount balance to target.
- Attendance present count is calculated and shown live; invalid day-off + absence combinations are blocked when saving.
- BM 360 score inputs are bounded by each pillar's maximum and totals are recalculated as inputs change.
- PNG reports use a cleaner navy/gold header, alternating rows, stronger typography and a footer.
- Save errors are surfaced instead of silently failing; history text is HTML-escaped.
- Service worker cache version bumped to v2 so browsers can update the app files.

## Validation performed in this build

A local JavaScript smoke-test harness checked: sales total across branches (Rs 2,500,000 from latest checkpoint values), 36.8% achievement against the Rs 6,800,000 target, attendance (16 − 2 − 1 = 13 present), rejection of attendance counts exceeding total staff, BM score summation (20/100), score clamping to a pillar's maximum (25), and saving a dated daily record. JavaScript syntax check passed. A full live GitHub deployment and on-device Android install still need to be verified after you upload this update.
