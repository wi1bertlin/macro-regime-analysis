# Macro Regime Analysis

## Overview
This project is a Python-based macroeconomic analysis tool that studies how different asset classes perform during changing economic conditions.

It uses inflation and industrial production data to classify each month into an economic regime, then compares the performance of equities, bonds, gold, and commodities.

---

## Features
- Download economic data from FRED
- Download historical asset prices using yfinance
- Measure inflation and economic growth
- Classify four macroeconomic regimes
- Compare asset returns and volatility by regime
- Identify the latest economic regime
- Visualise regime performance
- Test an illustrative regime-based portfolio
- Compare the strategy against SPY and an equal-weight portfolio

---

## Economic Regimes
- Goldilocks: Growth rising and inflation falling
- Reflation: Growth rising and inflation rising
- Stagflation: Growth falling and inflation rising
- Deflation: Growth falling and inflation falling

---

## Assets
- SPY: US equities
- TLT: Long-term US Treasury bonds
- GLD: Gold
- DBC: Commodities

---

## How It Works
The notebook:
1. Downloads market and economic data
2. Converts the data into monthly observations
3. Calculates annual inflation and industrial production growth
4. Measures whether growth and inflation are accelerating or slowing
5. Assigns each month to an economic regime
6. Calculates average asset returns and volatility in each regime
7. Creates charts to compare the results
8. Tests a simple regime portfolio using the previous month's signal

---

## Technologies Used
- Python
- Jupyter Notebook
- pandas
- numpy
- yfinance
- pandas-datareader
- matplotlib
- seaborn
- FRED economic data

---

## Data Sources
- FRED Consumer Price Index: https://fred.stlouisfed.org/series/CPIAUCSL
- FRED Industrial Production Index: https://fred.stlouisfed.org/series/INDPRO
- Yahoo Finance market data through yfinance

---

## How to Run

1. Install the required libraries:

    pip install -r macro_regime_requirements.txt

2. Open the notebook:

    macro_regime_analysis.ipynb

3. Run each block from top to bottom

---

## Key Learning
This project shows that asset performance can change when inflation and economic growth move in different directions.

It also demonstrates how an investment hypothesis can be converted into measurable rules, tested with historical data, and evaluated while considering signal timing and look-ahead bias.

---

## Important Limitation
The regime definitions and portfolio weights are simplified for educational purposes. Economic data is revised over time, and historical relationships may not continue in the future.

---

## Author
Ping-Hsiang (Wilbert) Lin
