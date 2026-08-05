# Impact of Major Events on GDP: A Data-Driven Analysis

Data science analysis of the economic impact of major sporting events (Olympics, FIFA World Cup) — cost/revenue modeling and forecasting through 2040 using Linear Regression and Random Forest Regressor in Python.

## Research Question

Do major international sporting events — specifically the Olympic Games and FIFA World Cup — lead to measurable, positive economic outcomes for host cities and countries when evaluated through the lens of cost versus revenue, and what financial patterns emerge from historical data that can inform predictions about future events?

## Dataset

- **Source:** [Peak Event: The Rise, Crisis and Potential Decline of the Olympic Games and the World Cup](https://doi.org/10.7910/DVN/82MMTK) (Müller, Gogishvili, Wolfe, Gaffney, Hug, & Leick, 2022), Harvard Dataverse
- **Coverage:** Summer Olympic Games, Winter Olympic Games, and FIFA World Cup, 1964–2020 (56-year span)
- **Key fields used:** venue costs, organization costs, ticketing/broadcast/sponsorship revenue, event year, event type

## Methodology

1. **Data Cleaning** — standardized currency fields (stripped `$`/commas), removed metadata and source columns, resolved inconsistent text entries (e.g. "No domestic sponsorship"), and aggregated sub-fields into unified Cost and Revenue columns.
2. **Exploratory Data Analysis** — visualized cost vs. revenue relationships, cost trends over time, and cost distribution by event type using Matplotlib.
3. **Model Training** — trained and compared Linear Regression and Random Forest Regressor models for two targets: revenue (predicted from cost) and cost (predicted from year), evaluating both with R² and Mean Absolute Error (MAE).
4. **Forecasting** — applied the best-performing model for each target to project cost, revenue, and profit/loss for 2032, 2036, and 2040.

## Results

- **Revenue model:** Random Forest Regressor outperformed Linear Regression (R² 0.223 vs. -0.412) and was selected for forecasting.
- **Cost model:** Linear Regression outperformed Random Forest for cost estimation (R² 0.109) and was selected for forecasting.
- **Forecast:** projected event costs rise from ~$6.0B (2032) to ~$6.6B (2040), while revenue stays flat around $1.5–1.8B, widening the projected loss from ~$4.2B to ~$5.1B by 2040.
- **Conclusion:** Major sporting events have consistently run at a financial loss for host nations, with the gap widening over time. Historical cost-to-revenue ratios rarely approach the break-even point, suggesting a need for structural reforms in event planning and funding.

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Scikit-Learn (`LinearRegression`, `RandomForestRegressor`, `train_test_split`, `r2_score`, `mean_absolute_error`)

## Repository Contents

| File | Description |
|---|---|
| `dataforprojectdatascience.py` | Data cleaning, exploratory analysis, model training, and forecasting pipeline |
| `DataScienceReport.pdf` | Full written report |
| `Impact of Major Events on GDP.pptx` | Presentation slides |

## Running the Code

This script was originally developed in Google Colab and expects the dataset at `/content/Growth dataset Olympic Games and Football World Cup.xlsx`. To run it locally, update `file_path` to point to your local copy of the dataset and install the dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn openpyxl
python dataforprojectdatascience.py
```

## Citation

Müller, M., Gogishvili, D., Wolfe, S. D., Gaffney, C., Hug, M., & Leick, A. (2022). *Dataset: Peak event: the rise, crisis and potential decline of the Olympic Games and the World Cup.* Harvard Dataverse. https://doi.org/10.7910/DVN/82MMTK
