# Macro Regime Analysis

## Research Question
Do equities, long-term government bonds, gold, and broad commodities behave differently when economic growth and inflation are accelerating or slowing?

I built this project to connect economic reasoning with market data. Rather than looking only for a price pattern, the notebook starts with a macroeconomic hypothesis: changes in growth and inflation should affect asset classes through different cash-flow, interest-rate, and risk channels.

## Data
### Economic indicators
The notebook downloads monthly data from the Federal Reserve Economic Data database:
- `CPIAUCSL`: US Consumer Price Index, used to calculate year-over-year inflation
- `INDPRO`: US Industrial Production Index, used as a simplified measure of economic growth

### Market proxies
Adjusted prices are downloaded through `yfinance`:
- `SPY`: US equities
- `TLT`: Long-term US Treasury bonds
- `GLD`: Gold
- `DBC`: Broad commodities

The analysis begins in 2007 so all four ETFs have overlapping observations.

## Regime Definition
I calculate year-over-year inflation and industrial-production growth, then measure each indicator's change over three months.

Each month is assigned to one of four regimes:

| Regime | Growth trend | Inflation trend |
|---|---:|---:|
| Goldilocks | Rising | Falling |
| Reflation | Rising | Rising |
| Stagflation | Falling | Rising |
| Deflation | Falling | Falling |

These names are simplified labels for the direction of the indicators, not official recession classifications.

## Methodology
1. Convert daily ETF prices into month-end prices and monthly returns.
2. Calculate 12-month changes in CPI and industrial production.
3. Calculate the three-month change in both annual growth rates.
4. Classify each month using the four-regime framework.
5. Join each regime with monthly asset returns.
6. Calculate annualised average return and volatility by regime.
7. Compare the historical growth of the four asset proxies.
8. Test an illustrative regime portfolio against SPY and an equal-weight portfolio.

For the strategy test, the regime is shifted by one month. This prevents the code from applying a month's regime to returns that occurred before that month had finished.

## Outputs and Interpretation
The notebook produces:
- A table showing the number and percentage of months in each regime
- Annualised asset-return and volatility tables by regime
- A heatmap comparing asset returns across regimes
- A growth-of-$1 chart for the four assets
- The latest regime based on available FRED data
- Performance statistics and an equity curve for the illustrative regime portfolio

The README does not state fixed return figures because the notebook uses an end date based on the day it is run. The purpose is to interpret the tables and charts, not to present a backtest result as a permanent fact.

## Illustrative Portfolio Rules
The regime portfolio uses predetermined weights that reflect a simple economic view. For example, it holds more equities in Goldilocks, more commodities and gold in Stagflation, and more long-term bonds in Deflation.

The weights are assumptions to test, not optimised recommendations.

## Limitations
- FRED data is revised, so the notebook uses the latest historical values rather than the exact data available to investors at each past date.
- CPI and industrial production are released with delays; a one-month shift only approximates real publication timing.
- The three-month trend rule and portfolio weights are subjective choices.
- Four ETFs cannot represent every security within each asset class.
- The sample begins in 2007 and contains a limited number of major economic cycles.
- Transaction costs, taxes, slippage, and portfolio turnover are not included.
- Historical regime relationships may not persist in the future.

## What I Learned
This project taught me how to turn a macroeconomic idea into explicit rules that can be tested. I also learned that avoiding look-ahead bias requires thinking about when information becomes available, not only how a calculation is written. The limitations were as important as the backtest because revised data and subjective definitions can make a historical strategy appear more reliable than it really is.

## How to Run

1. Install the dependencies:

    pip install -r requirements.txt

2. Open `macro_regime_analysis.ipynb` in Jupyter Notebook.
3. Run the cells from top to bottom.

## Data Sources
- FRED CPI: https://fred.stlouisfed.org/series/CPIAUCSL
- FRED Industrial Production: https://fred.stlouisfed.org/series/INDPRO
- Yahoo Finance market data through `yfinance`

## Author
Ping-Hsiang (Wilbert) Lin
