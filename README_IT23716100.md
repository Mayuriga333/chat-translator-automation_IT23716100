# Playwright Test Automation Project

This project automates the Chat Sinhala transliteration flow at https://www.pixelssuite.com/chat-translator using Python, Playwright, and openpyxl.

## Project Contents

- `test_automation.py` - Playwright automation runner provided for the assignment
- `generate_test_cases.py` - Generates the Excel workbook with 50 negative test cases
- `Assignment 1 - Test cases.xlsx` - Pre-filled workbook with 50 negative test cases
- `Commands.txt` - Exact run command for the automation

## Prerequisites

- Python 3.11 or Python 3.12
- Google Chrome
- Internet connection to access the application under test

## Install Dependencies

Run the following command in the `test_automation` folder:

```bash
pip install playwright openpyxl && playwright install
```

## Generate The Excel File

If you need to recreate the workbook, run:

```bash
python generate_test_cases.py
```

This creates `Assignment 1 - Test cases.xlsx` with the sheet name ` Test cases` and the following columns:

- Test Case ID
- Input length type
- Input
- Expected output
- Actual output
- Status
- Singlish input types covered
- Evidence or rationale for the input type covered

`Actual output` and `Status` are intentionally left empty by the generator because `test_automation.py` fills them during execution.

## Run The Tests

Use this exact command:

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

## Notes

- The workbook contains 50 negative test cases for the Chat Sinhala transliteration function.
- All test case IDs begin with `Neg_`.
- The sheet name includes a leading space: ` Test cases`.
- The automation writes the actual transliteration output and the final status back to the Excel file.