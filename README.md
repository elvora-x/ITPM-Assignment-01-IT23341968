# Assignment 1 - Transliteration Accuracy Testing
## IT3040 – ITPM | Option 1

This project automates the testing of the [PixelsSuite Chat Translator](https://www.pixelssuite.com/chat-translator) using Playwright and Python. It evaluates how accurately the application converts chat-style Singlish input into Sinhala output.

---

## Project Structure

```
test_automation/
│
├── test_automation.py          # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Excel file containing test cases and results
└── README.md                   # This file
```

---

## Prerequisites

Before running the tests, make sure the following are installed on your machine:

- **Python 3.11 or 3.12** — [Download here](https://www.python.org/downloads/)
- **Google Chrome** (recommended) — [Download here](https://www.google.com/chrome/)

---

## Installation

### Step 1 — Clone or extract the project

Extract the project ZIP file and navigate to the `test_automation` folder.

### Step 2 — Install required dependencies

Open **Command Prompt** or **PowerShell**, navigate to the `test_automation` folder, and run the following commands:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

> Note: If `pip install -U pip` gives an error, run this instead:
> ```bash
> python -m pip install -U pip
> ```

---

## How to Run the Tests

### Step 1 — Fill in the Excel file

Open `Assignment 1 - Test cases.xlsx` and make sure your test cases are entered under the following columns:
- `TC ID`
- `Input length type`
- `Input`
- `Expected output`

> ⚠️ Do NOT enter values in the `Actual output` or `Status` columns — these are filled automatically by the script.

### Step 2 — Navigate to the project folder

```bash
cd path\to\test_automation
```

For example:
```bash
cd C:\Users\ASUS\OneDrive\Desktop\IT23341968\test_automation
```

### Step 3 — Run the automation script

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Step 4 — Check the results

Once the script finishes, reopen the Excel file. The `Actual output` and `Status` (Pass/Fail) columns will be automatically populated.

---

## Command Parameters Explained

| Parameter | Value | Description |
|---|---|---|
| `--excel` | `"Assignment 1 - Test cases.xlsx"` | Path to the Excel test cases file |
| `--url` | `"https://www.pixelssuite.com/chat-translator"` | URL of the application under test |
| `--wait-ms` | `5000` | Wait time in milliseconds after each translation |
| `--type-delay-ms` | `80` | Delay between keystrokes when typing input |
| `--slow-mo-ms` | `200` | Slow motion delay for browser actions |
| `--save-every` | `1` | Save results to Excel after every test case |
| `--keep-open` | — | Keep the browser open after the script finishes |

---

## Notes

- Do not open the Excel file while the script is running, as this may cause save errors.
- The script uses Chromium by default. Google Chrome is recommended for best results.
- All 50 test cases cover failures across 24 Singlish input types as defined in Appendix 1 of the assignment.
