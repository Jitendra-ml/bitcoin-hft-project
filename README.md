# bitcoin-hft-project

## Project Overview

This project builds a **complete trading pipeline** for Bitcoin 1-minute data (3.1M records, 2017-2023). It bridges **quant finance** (statistical arbitrage, backtesting) and **machine learning** (anomaly detection, XGBoost signals).

## 📊 Dataset

| Property | Value |
|----------|-------|
| **Source** | Binance API via Kaggle |
| **Timeframe** | August 2017 - July 2023 (6 years) |
| **Rows** | 3,126,000 |
| **Granularity** | 1-minute OHLCV |
| **Size** | 333 MB (compressed) |

# 01_data_validation.ipynb

## Overview

This notebook performs **data validation** on the Bitcoin 1-minute dataset (3.1M records, 2017-2023). It ensures data quality, identifies missing minutes, and validates OHLC integrity before feature engineering.

---

## What This Notebook Does

| Validation Step | Method | Why It Matters |
|----------------|--------|----------------|
| **Timestamp validation** | Convert to datetime, check range | Ensures time series integrity |
| **Missing minute detection** | Compare actual vs. expected 1-min intervals | Identifies gaps for backtesting |
| **OHLC integrity** | Verify high ≥ low, close within range | Prevents data errors |
| **Order flow validation** | Check taker buy volume ≤ total volume | Ensures microstructure data quality |
| **Trade activity analysis** | Analyze `number_of_trades` distribution | Validates market activity patterns |

---
