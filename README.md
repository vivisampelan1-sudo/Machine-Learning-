# Machine Learning Approach to Volatility Forecasting

**Individual Coursework — IFTE0005: Corporate Financial Strategy and Capital Structure**

Replication of [Christensen, Siggaard & Veliyev (2023)](https://doi.org/10.1093/jjfinec/nbac020), testing whether Random Forest outperforms the HAR model for realized volatility forecasting.

## Overview

This project compares the Heterogeneous Autoregressive (HAR) model against a Random Forest (RF) regressor using minute-level intraday data for three U.S. equities: AAPL, AMZN, and JPM (2016–2023).

Two feature sets are tested:
- **MHAR**: RV lags only (daily, weekly, monthly)
- **MALL**: RV lags + VIX + Volume + Momentum

## Key Results

| Stock | MHAR RF/HAR | MALL RF/HAR | MALL Winner |
|-------|-------------|-------------|-------------|
| AAPL  | 1.6343      | 1.0476      | HAR         |
| AMZN  | 1.7430      | 1.0464      | HAR         |
| JPM   | 1.1157      | 0.7443      | **RF**      |
| **Avg** | **1.4977** | **0.9461** | **RF**      |

RF underperforms HAR with RV lags alone, but outperforms when given richer features — particularly for JPM, where VIX captures market-wide volatility drivers.

## Repository Structure
├── Machine_Learning_Personal_Coursework.ipynb   # Full pipeline (Colab)
└── README.md

## How to Run

1. Open `Machine_Learning_Personal_Coursework.ipynb` in [Google Colab](https://colab.research.google.com/)
2. Upload minute-level price data (AAPL.txt, AMZN.txt, JPM.txt) to Google Drive under `/data4rv/`
3. Run all cells

## Dependencies

- Python 3.x
- numpy, pandas, matplotlib
- scikit-learn
- yfinance (for VIX data)

## References

- Christensen, K., Siggaard, M., & Veliyev, B. (2023). A Machine Learning Approach to Volatility Forecasting. *Journal of Financial Econometrics*, 21(5), 1680–1727.
- Corsi, F. (2009). A Simple Approximate Long-Memory Model of Realized Volatility. *Journal of Financial Econometrics*, 7(2), 174–196.
- Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5–32.

## Author

Vivi Agustini Sampelan — UCL, 2026
