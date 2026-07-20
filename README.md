# BOL Heat Chemistry Lookup

This Streamlit app reads Excel coil lists and PDF mill test certificates, then reports heat-level chemistry, mechanical properties, and standards compliance.

## Run Locally

1. Double-click `run_app.bat`, or run the command below from this folder:

```powershell
python -m streamlit run app.py
```

2. Upload one or more Excel or PDF files.
3. Verify the column selections in the sidebar:
   - BOL column
   - Coil column
   - Heat column
   - Material Spec column
   - Element columns
   - Mechanical columns
4. Enter a BOL number, or leave it blank to report all uploaded rows/coils.
5. Download the Excel report or PDF compliance report.

## Notes

- `FULL_TAG_NUM` is treated as the coil number when available.
- Text-based PDFs are supported. Scanned/image-only PDFs may require OCR.
- Standard limits are stored in `standards_rules.csv`.
- `Min` checks a lower limit, `Max` checks an upper limit, and both together check an acceptable range.
- The PDF compliance report highlights failed, missing, and unchecked values.
