# Unemployment Analysis with Python

## Overview
This project analyzes unemployment trends across Indian states using the Centre for Monitoring Indian Economy (CMIE)-style unemployment dataset (`India.csv`). The goal is to explore how unemployment rates vary by region and time, and to measure the impact of the COVID-19 pandemic on employment.

## Dataset
- **File:** `India.csv`
- **Key columns:** Region, Date, Frequency, Estimated Unemployment Rate (%), Estimated Employed, Estimated Labour Participation Rate (%), Area

## Approach
1. **Data Cleaning** — Stripped whitespace from column names and text fields, converted `Date` to datetime, removed null values and duplicates, and extracted `Year`/`Month` fields.
2. **Exploratory Data Analysis**
   - Computed region-wise average unemployment rate.
   - Analyzed month-wise unemployment trends nationally.
   - Plotted time-series unemployment rates for individual states.
   - Visualized the top 10 states by average unemployment rate.
   - Built a correlation heatmap between unemployment rate, employment, and labour participation rate.
3. **COVID-19 Impact Analysis** — Split the data at the COVID-19 lockdown start date (25 March 2020) and compared pre- vs. post-COVID averages.

## Key Findings
- **Highest average unemployment (pre/post combined):** Tripura, Haryana, and Jharkhand recorded the highest average unemployment rates among all states/UTs.
- **COVID-19 impact:**
  | Metric | Pre-COVID | Post-COVID |
  |---|---|---|
  | Avg. Unemployment Rate (%) | 9.51 | 17.77 |
  | Avg. Estimated Employed | 7.47M | 6.52M |
  | Avg. Labour Participation Rate (%) | 43.89 | 39.33 |

  The unemployment rate nearly doubled after the onset of COVID-19, accompanied by a drop in both the number of people employed and labour force participation.

## Tech Stack
- Python
- pandas, NumPy
- Matplotlib, Seaborn

## How to Run
1. Place `India.csv` in the same directory as the notebook.
2. Install dependencies: `pip install pandas numpy matplotlib seaborn`
3. Open and run `Unemployment_Analysis.ipynb` cell by cell in Jupyter Notebook.

## Project Structure
```
DataScience-Task2-UnemploymentAnalysis/
├── Unemployment_Analysis.ipynb
├── India.csv
├── README.md
└── screenshots/
```
