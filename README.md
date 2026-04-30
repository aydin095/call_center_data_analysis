# call_center_data_analysis

# 911 Calls — Exploratory Data Analysis

Exploratory data analysis of the **Montgomery County, PA 911 calls** dataset using Python. The project investigates call volume by location, classifies emergencies by type (EMS, Fire, Traffic), and visualizes how calls are distributed across hours, days, and months.

## Dataset

- **Source:** Kaggle — *911.csv* (Montgomery County, PA emergency calls)
- **Key columns used:** `zip`, `twp` (township), `title`, `timeStamp`
- The notebook expects the file at `911.csv` (originally loaded from Google Drive in Colab).

## Tech Stack

- Python 3
- pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

## Questions Explored

1. What are the **top 5 zip codes** for 911 calls?
2. What are the **top 5 townships** for 911 calls?
3. How many **unique call titles** are there?
4. What is the distribution of calls by **reason** (EMS / Fire / Traffic)?
5. How do calls vary by **hour, day of week, and month**?
6. How do **specific reasons** (Traffic, EMS, Fire) trend over time?

## Analysis Steps

- Loaded the CSV and inspected schema with `info()` / `head()`.
- Engineered a **`reason`** column by splitting the `title` field (e.g., `EMS: BACK PAINS/INJURY` → `EMS`).
- Converted `timeStamp` to a datetime and extracted **`hour`**, **`month`**, and **`day of week`** features.
- Mapped numeric weekdays to labels (`Mon`, `Tue`, …, `Sun`).
- Grouped by date / month / day-hour combinations to study temporal trends.

## Visualizations

- Countplots of calls by **reason**, **day of week**, and **month** (with `reason` as hue)
- Line plots of monthly call counts and per-reason daily trends (Traffic / EMS / Fire)
- `lmplot` regression of monthly call volume
- **Heatmaps** of:
  - Day of week × Hour
  - Day of week × Month

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. Place `911.csv` in the project root (or update the path in the notebook).
4. Open the notebook:
   ```bash
   jupyter notebook Untitled10.ipynb
   ```
   Or upload it to **Google Colab** and mount your Drive as in the original notebook.

## Project Structure

```
.
├── Untitled10.ipynb     # main EDA notebook
├── 911.csv              # dataset (not included — download separately)
└── README.md
```

## Key Takeaways

- **EMS** is consistently the most common call reason.
- Call volume shows clear **weekly** and **hourly** patterns — visible in the heatmaps.
- A handful of zip codes and townships account for the majority of calls.

## License

This project is released under the MIT License.

## Author

Created as part of a data analytics learning journey. Feedback and pull requests are welcome.
