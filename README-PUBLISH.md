# BATIK ASM & BM 360° — v3 update

## Publish to GitHub Pages
1. Extract this ZIP.
2. Upload the contents of `BATIK_ASM_BM360_PWA_v3` to the repository root, replacing `index.html`, `service-worker.js`, and `manifest.json`; upload the `icons` folder if prompted.
3. Commit to `main`, wait for GitHub Pages deployment to succeed.
4. On phone, close the installed app completely and reopen it. If stale, open the website in Chrome and reload once to refresh the service worker.

## Important
- Existing local data is stored in browser storage on each device. Export a JSON backup before replacing/reinstalling anything. This version keeps the same storage key for existing records.
- Sales checkpoint form remains separate from nightly closing. The sales form uses the existing checkpoint inputs; validate your local workflow after deployment.
- Closing supports six outlets, optional screenshot preview, manually reviewed values, formula calculations, save/history, and PNG sharing. It does not perform OCR automatically; the screenshots are attached for visual reference only.
- Forecast formula uses actual calendar days: forecast = MTD achieved / elapsed days × days in month. Confirm the official company convention before using forecasts for management decisions.


## Screenshot reader (v4)
- Open Closing report and select one or more branch closing screenshots in “Screenshot reader”.
- Tap “Read screenshots”. The browser uses Tesseract.js OCR and attempts to detect the outlet code and closing values.
- Check every extracted field in the outlet forms before saving or sharing. OCR may misread digits, particularly low-resolution screenshots; it is an assistant, not an authoritative source.
- First use requires an internet connection to load the OCR engine and English language model. The app's other forms remain available offline, but OCR may not work offline until those resources have been cached by the browser.
- OCR runs in the browser; screenshots are not intentionally uploaded to a server by this feature.
- If the outlet code is not detected or a value is missing, enter it manually. Duplicate screenshots should not be imported twice.
