# Week 3: Python & Data Wrangling

Assignment: clean a messy dataset in Pandas — handle missing values, filter rows, create new columns.

## Files
| File | Description |
|------|-------------|
| `data.csv` | Original messy dataset (daily workout log, Dec 2020) |
| `data_wrangling.ipynb` | Full notebook: inspection, cleaning, filtering, new columns, visualization |
| `cleaned_data.csv` | Final cleaned dataset (31 rows, no missing values) |
| `plots.png` | Matplotlib & Seaborn charts |

## Problems found in `data.csv` and how they were fixed
| Problem | Fix |
|---------|-----|
| Dates stored as text with stray quotes (`'2020/12/01'`) | Removed quotes, converted to `datetime` |
| One date in another format (`20201226`) | Parsed with a separate format |
| 1 missing date | Filled as 22 Dec 2020 (daily log, neighbours are 21 & 23 Dec) |
| 1 duplicate row (12 Dec) | Dropped (32 → 31 rows) |
| `Duration = 450` outlier | Corrected to 45 (typo; all others are 30–60) |
| `Pulse` > `Maxpulse` on 23 Dec | Values were swapped — swapped back |
| 2 missing `Calories` | Filled with median Calories of workouts with the same Duration |

## Filtering
- 60-min workouts with Calories > 350
- Maxpulse > 140
- Workouts from 16 Dec onward

## New columns
`Weekday`, `Week`, `Calories_per_min`, `Pulse_Ratio`, `Intensity` (Low / Medium / High), `Is_Weekend`

## Run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook data_wrangling.ipynb
```
