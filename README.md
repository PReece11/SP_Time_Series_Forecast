# SPY Time Series Forecast (SARIMAX)
Forecasting short-term SPY (S&P 500 ETF) returns using a SARIMAX(1,0,1) model with exogenous predictors.

## Why this project
Financial markets are noisy and shock-driven. This project evaluates whether adding volatility (VIX) and a macro signal (US 10Y Treasury yields, DGS10) improves short-term forecasting relative to a baseline ARIMA model.

## Data
Daily combined dataset including:
- **SPY** prices → transformed to **log returns** (target)
- **VIX** → log returns
- **US 10-Year Treasury yield (DGS10)** → basis-point changes, lagged
- **Bitcoin** was explored but excluded from the final model

## Methods
- Stationarity checks (**ADF**)
- **ACF/PACF** for order intuition
- **Granger causality** to validate exogenous predictors
- Baseline: **ARIMA(1,0,1)**
- Final: **SARIMAX(1,0,1)** with:
  - **VIX (lag 1)**
  - **DGS10 (lag 4)**
- Diagnostics: **Ljung–Box** + residual distribution checks

## Results
- **RMSE:** 6.17  
- **MAE:** 5.17  
- Key drivers: **VIX (lag 1)** and **DGS10 (lag 4)**
- Forecast plot:  
  ![Forecast Output](visuals/forecast_vs_actuals.png?raw=1)

## Repo contents
- `notebooks/` — end-to-end analysis notebooks
- `src/` — reusable code (loading, preprocessing, modeling, evaluation)
- `visuals/` — exported charts/figures
- `docs/` — write-up (optional)

## Quickstart
```bash
pip install -r requirements.txt
```

## Authors

- Paula Reece
- Sarah Her
- Yvonne Zhang
- Matthew Duffy

## Contact

📫 **Paula Reece**  
🔗 LinkedIn: https://www.linkedin.com/in/paulasreece/  
✉️ Email: dataopsbypaula@gmail.com

