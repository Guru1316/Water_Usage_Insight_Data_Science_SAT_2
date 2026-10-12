# Water Usage Insight — VS Code (Round 2)

All data in this academic project are synthetic.

## Setup
1. Extract this project folder.
2. Open the folder in VS Code.
3. Ensure the five CSVs are inside `data/`.
4. Open a terminal in this folder and install dependencies:

```bash
python -m pip install -r requirements.txt
```

5. Run:

```bash
python round2.py
```

On Windows, if `python` is unavailable, try `py round2.py`.

The script writes cleaned datasets, quality reports, EDA tables, engineered features and charts to `outputs/`.

## Important cleaning choices
- Exact duplicate meter rows are removed.
- Negative usage is treated as invalid and excluded from usage analysis.
- Missing usage rows are excluded rather than imputed without evidence.
- Connection types are standardized.
- Unmatched maintenance rows are preserved separately as exceptions.
- Daily analysis is merged by connection and date; billing remains a monthly table and is not duplicated across daily readings.
