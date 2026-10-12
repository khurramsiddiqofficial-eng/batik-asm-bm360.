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


## v12 Daily Closing workflow
- Import the original monthly North Zone workbook (containing `All Store ` and `Central ` sheets) as the workbook template.
- In Daily Closing, select a date and enter only Quantity Sold and Total Sale Amount for each outlet. Save entries; they persist locally by date.
- Download updated Excel to write every saved date into All Store, update row/column totals, and refresh Central formulas. Open the exported workbook in Excel so formulas recalculate.
- Closing report preview has been cleaned: the generic “Generated from entered data / verify figures” text has been removed.
- App data is still local to the device; export a JSON backup before replacing deployed files. The imported workbook template is held in memory for the current session, so import the workbook again after reopening the app before exporting.
