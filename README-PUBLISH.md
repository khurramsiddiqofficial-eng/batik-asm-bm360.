# BATIK ASM & BM 360° — Formula and Report Quality Update

## Included
- Existing sales screenshot reader and closing screenshot reader retained.
- PNG reports restyled with a navy header, gold divider, readable table headers, alternating row shading, stronger total row, and generated timestamp/footer.
- BM 360° score inputs start at zero to avoid accidentally presenting a perfect score before assessment.
- Closing report labels positive variance as Deficit and negative variance as Access.
- Closing save checks date/day-count validity and warns before saving when daily sale does not equal cash plus card.

## Publish
1. Export a JSON backup from the currently installed app.
2. Extract this ZIP.
3. Upload the contents of `BATIK_ASM_BM360_PWA_v6_Formula_Report_Audit` to the repository root, replacing existing files.
4. Commit to `main` and wait for GitHub Pages deployment.
5. Reopen/refresh the installed PWA and test with sample records before live use.

## Formula notes / limitations
- Sales checkpoint grouping is configured as 12 PM + 1 PM + 2 PM; 3 PM + 4 PM; 5 PM + 6 PM; 7 PM + 8 PM. This assumes each entered column is sales for that hour only.
- Closing forecast uses MTD achieved / elapsed days * days in month. Desired performance uses monthly target * elapsed days / days in month. Remaining target is monthly target - MTD achieved. Required daily average uses remaining target / remaining calendar days.
- Screenshot OCR is best-effort; values must be reviewed against the screenshot. The OCR reader is not reliable enough to auto-approve financial values.
- Local tests performed: JavaScript syntax check passed. This package has not been validated on the live site or every Android device. Test formulas and PNGs after deployment before using official reports.


## v8 OCR safety changes
- Hourly OCR no longer guesses values from the final lines of recognized text.
- If a unique, explicit nine-cell hourly total row is not detected, all hourly suggestions remain blank.
- Branch must be manually confirmed for every screenshot before applying.
- Duplicate destination hours are blocked; existing sales values trigger an overwrite confirmation.
- OCR output remains a suggestion. Compare each figure with the source screenshot before applying.
- Test with one known screenshot per reporting line before using for live reporting.
