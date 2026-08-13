# Sales Prediction Using Python

## Overview
This project builds a regression model to predict product sales based on advertising spend across three channels: TV, Radio, and Newspaper. It compares a simple linear model against an ensemble model to see which captures the relationship best.

## Dataset
- **File:** `Advertising.csv`
- **Columns:** TV, radio, newspaper (spend in each channel), sales (target variable)
- 200 records, no missing values.

## Approach
1. **EDA** — Checked for nulls/duplicates, reviewed descriptive statistics, and visualized relationships with pairplots and per-channel scatter plots (Sales vs. TV, Radio, Newspaper).
2. **Correlation Analysis** — Built a correlation heatmap; TV spend showed the strongest correlation with Sales (0.78), followed by Radio (0.58) and Newspaper (0.23).
3. **Modeling** — Split data 80/20 into train/test sets and trained two models:
   - Linear Regression (baseline)
   - Random Forest Regressor (100 estimators)
4. **Evaluation** — Compared models using MAE, RMSE, and R².
5. **Residual Analysis** — Plotted residuals for the best-performing model to check for systematic errors.
6. **Feature Impact** — Compared Linear Regression coefficients and Random Forest feature importances to identify which channel drives sales most.

## Results

| Model | MAE | RMSE | R² |
|---|---|---|---|
| Linear Regression | 1.461 | 1.782 | 0.899 |
| Random Forest | 0.620 | 0.769 | **0.981** |

**Random Forest outperformed Linear Regression** on every metric, capturing non-linear relationships in the data that the linear model missed.

**Feature impact:**
- Linear Regression coefficients ranked Radio highest, followed by TV, then Newspaper.
- Random Forest feature importances ranked **TV** highest (0.62), followed by Radio (0.36), with Newspaper contributing very little (0.01).
- **TV advertising spend has the strongest overall impact on sales**, followed by Radio; Newspaper spend shows minimal effect and could likely be deprioritized in future ad budgets.

## Tech Stack
- Python
- pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn (LinearRegression, RandomForestRegressor)

## How to Run
1. Place `Advertising.csv` in the same directory as the notebook.
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Open and run `sales_prediction.ipynb` cell by cell in Jupyter Notebook.

## Project Structure
```
DataScience-Task5-SalesPrediction/
├── sales_prediction.ipynb
├── Advertising.csv
├── README.md
└── screenshots/
```
