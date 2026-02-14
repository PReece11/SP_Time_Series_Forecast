# Data

This project uses daily time series data for:

- SPY (S&P 500 ETF)
- VIX (Volatility Index)
- US 10-Year Treasury Yield (DGS10 from FRED)

The full dataset is not stored in this repository due to size and licensing considerations.

To reproduce the analysis:
1. Download historical SPY and VIX data.
2. Download DGS10 data from FRED.
3. Merge datasets by date.
4. Place the cleaned dataset inside this `data/` directory.