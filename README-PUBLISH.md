# BATIK ASM & BM 360° — v5 Sales + Closing Screenshot Readers

## Publish to GitHub Pages
1. Export a JSON backup from the app on each device before replacing files.
2. Extract this ZIP.
3. Upload the contents of `BATIK_ASM_BM360_PWA_v5_Sales_Screenshot_Reader` to the repository root, replacing `index.html`, `service-worker.js`, and `manifest.json`; upload/replace the `icons` folder if prompted.
4. Commit to `main` and wait for the GitHub Pages deployment to succeed.
5. On phone, close the installed app completely. Open the website in Chrome and reload it, then reopen the installed app. The v5 service-worker cache name forces a new cache to be installed.

## Screenshot readers
- **Sales reports:** open Sales reports, select one or more staff-wise hourly sales screenshots, tap Read sales screenshots, check the detected branch and each hourly total, correct any mistakes, and tap Apply verified hourly figures. F-10 outlet 1022/23 is treated as one combined sales-report line.
- **Closing reports:** open Closing report, select closing screenshots, tap Read screenshots, then review the detected outlet and figures before saving.
- Both readers use browser-based Tesseract.js OCR. First use requires internet access to load the OCR engine and English language data. Screenshots are not intentionally uploaded to a server by these features.

## Important safeguards and limitations
- OCR is imperfect. Always review the outlet code and every amount before saving or sharing. For sales screenshots, the reader attempts to suggest hourly totals from the footer; if it cannot reliably detect the totals, enter them in the editable fields shown in the reader. It does not safely infer every individual staff row.
- Sales columns represent **hourly sales**, not cumulative totals: 12 PM + 1 PM + 2 PM feed the 2 PM checkpoint; 3 PM + 4 PM feed 4 PM; 5 PM + 6 PM feed 6 PM; 7 PM + 8 PM feed 8 PM. Blank hour fields are left blank.
- Closing keeps six outlet records, including 1022 and 1023 separately. Sales reporting keeps the combined F-10 1022/23 line.
- Local records remain stored in browser storage on each device. Export a JSON backup before replacing files; data on the laptop does not automatically sync to mobile.
