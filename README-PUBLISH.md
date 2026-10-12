# BATIK ASM & BM 360° — v10 Mobile Manual Entry

## What's improved
- Hourly sales screenshot reader is fully manual. Each hour has a large, labeled amount field in a mobile-friendly two-column layout; no hour dropdowns or OCR guesses.
- Screenshot preview remains visible above the entry fields, with an option to open it full-screen.
- Closing report now uses the same manual workflow: select closing screenshots, inspect each image, choose the outlet, enter only the figures visible, and apply them to that outlet.
- Closing fields cover daily total sale, cash, card, cash in hand, units sold, units in hand, invoices, MTD achieved, monthly target, target quantity and MTD units achieved.
- Existing values trigger a replacement confirmation. Blank fields are not applied. The app still requires users to verify calculations and save the closing report separately.
- Service-worker cache name updated to v10.

## Publish
1. Export a JSON backup from the existing app (History & backup).
2. Extract this ZIP.
3. Upload the **contents** of the `BATIK_ASM_BM360_PWA_v10_Mobile_Manual_Entry` folder to the root of the existing GitHub repository, replacing prior files.
4. Commit to `main` and wait for GitHub Pages deployment.
5. Reopen/refresh the installed PWA. If it shows the old version, close it fully and reopen after deployment.

## Notes
- The app stores data locally on each device. Export backups regularly; desktop and phone data do not automatically sync.
- Screenshot images are used only as visual references in the browser; no OCR runs in either manual reader.
- Review outlet selection and figures before applying. Review totals and cash + card reconciliation before saving a closing report.
- JavaScript syntax was checked with Node. Browser and Android interaction testing still needs to be performed on the deployed app.


## v11 — Excel closing workbook + BM 360 customer reviews
- Closing tab: import the North Zone Excel workbook (`All Store` and `Central` sheets) to load daily sales, units, MTD achieved and targets for the selected date.
- Manual fields not present in the workbook (cash, card, cash in hand, stock and invoices) remain blank for manual entry; always verify imported values before saving.
- Export updated workbook to write app-entered daily values back into `All Store`, update `Central` forecast formulas using the actual month length, and add `App Closing Report` and `App BM360` sheets.
- BM 360: review target and reviews received fields; review score is calculated automatically out of 5, and Customer Experience/Complaints is separately scored out of 5, preserving 100 total points.
- Excel import/export uses the SheetJS library from a CDN, so an internet connection is needed when the app first loads the library. Existing manual entry and PNG report features remain available.
- Before deployment: export an app JSON backup. Upload the ZIP contents to the GitHub Pages repository root, replace existing files, commit, then reopen the installed PWA after deployment.
