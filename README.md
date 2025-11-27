# 🌐 Crypto Statistical Arbitrage using Cointegration  
### Johansen Test · Engle–Granger · Kalman Filter · Z-Score Mean Reversion

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Domain-Quant%20Finance-00A86B?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Exchange-Binance%20US-F3BA2F?style=for-the-badge&logo=binance&logoColor=white" />
  <img src="https://img.shields.io/badge/Stats-statsmodels%20%7C%20pykalman-4B8BBE?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Backtesting-Completed-00C853?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-informational?style=for-the-badge" />
</p>

---

## 📽️ Strategy Pipeline (GIF Overview)

<p align="center">
  <img src="assets/gifs/hourly_pipeline.gif" alt="Hourly Johansen–Kalman pipeline" width="720" />
</p>

<p align="center">
  <img src="assets/gifs/daily_pipeline.gif" alt="Daily Engle–Granger pipeline" width="720" />
</p>

> 🎥 Put your own GIFs at: `assets/gifs/hourly_pipeline.gif` and `assets/gifs/daily_pipeline.gif`.

---

## 📌 Overview

This project builds a complete **statistical arbitrage framework** for cryptocurrency pairs using both hourly and daily data:

- **Johansen Cointegration** to detect multi-asset long-run relationships  
- **Kalman Filter** to estimate dynamic hedge ratios over time  
- **Z-Score Mean Reversion** rules for trade entry/exit  
- **Engle–Granger** cointegration for simpler 2-asset daily pairs  
- A lightweight **backtesting engine** to evaluate performance

Assets: **BTC, ETH, LTC, ADA, DOT, XRP, XLM**  
Data sources: **Binance US** (hourly) and **Yahoo Finance** (daily).

📄 Full write-up: `report/Computational_Investment_Report.pdf`

---

## 🧠 Project Architecture

```text
crypto-pairs-trading/
│
├── notebooks/
│   └── pairs_trading_analysis.ipynb
│
├── src/
│   ├── data_loading.py
│   ├── cointegration.py
│   ├── kalman_filtering.py
│   ├── signals.py
│   ├── backtesting.py
│   ├── plotting.py
│   ├── run_hourly.py
│
│
├── report/
│   └── Computational_Investment_Report.pdf
│
├── assets/
│   └── gifs/
│       ├── hourly_pipeline.gif
│       └── daily_pipeline.gif
│
├── requirements.txt
└── README.md
```
🚀 Key Components
🔹 1. Johansen Cointegration (Hourly)

Tests cointegration for pairs like BTC–ETH, ETH–LTC, DOT–ADA

Uses trace statistic vs critical value for significance

Suitable for multi-asset relationships

🔹 2. Kalman Filter (Dynamic Hedge Ratios)

State-space model for time-varying intercept and hedge ratio

Trading rules (typical):
Go LONG spread   when Z < -2
Go SHORT spread  when Z > +2
Exit to FLAT     when Z crosses 0

🔹 5. Backtesting

Computes PnL from spread changes × position

Tracks equity curve, returns, and basic performance stats

Supports both hourly and daily strategies

📊 Performance Summary

⭐ Hourly Johansen Strategy

Pair	Result	Profit / Loss %
BTC–ETH	Cointegrated	23.52%
BTC–LTC	Cointegrated	7.46%
ETH–LTC	Cointegrated	11.84%
DOT–ADA	Cointegrated	24.48%
XRP–XLM	Not cointegrated	N/A


📈 Outputs & Visuals

The project generates:

Rolling hedge ratio plots

Z-score time series with entry/exit bands

Spread evolution over time

Capital growth / equity curves
