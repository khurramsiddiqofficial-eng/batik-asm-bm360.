# BATIK ASM & BM 360° — Heading-Focused Screenshot Review Update (v8)

## What changed
- Sales screenshots: preview selected images, detect/suggest the reporting line from visible outlet identifiers, and keep the editable hour-to-field review table. Confirm branch and values before applying.
- Closing screenshots: preview selected images and extract values by nearby report headings such as Total Sale, Cash Sale, Card Sale, Cash in Hand, Units Sold, Units in Hand, Target Value, and Achieved.
- Closing OCR now presents an editable review table for every screenshot. Each row has a recognized heading, a selectable destination field, an editable number, and a clear action.
- The closing reader no longer writes recognized values into the report automatically. The user must select the outlet and press “Apply reviewed values.”
- Duplicate destination mappings are blocked to prevent two OCR rows silently overwriting the same closing field.
- Both readers show selected screenshot previews and preserve recognized text for troubleshooting.

## Publish
1. Export a JSON backup from the currently installed app.
2. Extract this ZIP.
3. Upload the contents of `BATIK_ASM_BM360_PWA_v6_Formula_Report_Audit` to the root of the existing GitHub repository, replacing `index.html` and `README-PUBLISH.md` as applicable. Keep existing `manifest.json`, `service-worker.js`, and icon files in the repository.
4. Commit to `main` and wait for GitHub Pages deployment.
5. Close/reopen the installed PWA or refresh it after deployment. If an older cached version remains, fully close the app and reopen it after the service worker updates.

## Important limits
- OCR is best-effort, not guaranteed. Heading-focused extraction reduces field-mapping errors but cannot guarantee every number is read correctly from every screenshot.
- Always compare outlet, headings and values against the original screenshot before applying. Do not use unverified OCR for official financial reporting.
- JavaScript syntax check passed. This package has not been browser-tested on all screenshots/devices or validated on the live Pages site. Test with one known sales screenshot and one known closing screenshot before live use.
