# Source
[FreeCodeCamp: Algorithmic Trading Using Python - Full Course](https://www.youtube.com/watch?v=xfzGZB4HhEE)

# Technical Setup (1-2 to activate, 1-4 to setup)
1. Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
2. .venv\Scripts\Activate.ps1
3. python -m ipykernel install --user --name=SP5000_EqualWeights --display-name "Python (.venv) SP5000_EqualWeights"
4. pip install -r requirements.txt

# Workbook Summaries
## General
The course emphasizes on using the IEX Cloud API. Since the endpoint is not supported, I've decided to use the yfinance (Yahoo Finance) library to pull the relevant market data.

## Equal-Weight S&P 500 Index Fund
A Workbook that accepts the value of an investment and tell how many shares of each S&P 500 constituent you should purchase to get an equal-weight version of the index fund.

## Quantitative Momentum Strategy
A Workbook that simulates an investing strategy that selects the 50 stocks from an equal-weight portfolio (S&P 500 from the first Workbook) with the highest price momentum.

**Momentum**: Price increase over a specified time interval.
- Hiqh-Quality Momentum Stocks: Slow and steady outperformance over longer periods of time
- Low-Quality Momentum Stocks: No or low momentum with a sudden surge upwards
- Realisitc Momentum Strategy: Using multiple time periods (e.g. 1m, 3m, 6m, 1y) for calculating a mean of the price momentums

## Quantitative Value Strategy
A Workbook that simulates an investing strategy which selects the 50 stocks from an equal-weight portfolio (S&P 500 from the first Workbook) with the best value metrics.

**Value Investing**: investing in the stocks that are cheapest relative to common measures of business values (earnings, assets, etc.)

Business values used in this workbook:
- Price-to-earnings ratio
- Price-to-book ratio
- Price-to-sales ratio
- Enterprise Value divided by Earnings Before Interest, Taxes, Deprecation, and Amortization (EV/EBITDA)
- Enterprise Value divided by Gross Profit (EV/GP)

Each of these values are ranked relative to other stocks and a percentage is thrown as a rank (0 to 1) indicating the percentile. The mean of all the rankings of the business values are then calculated to evaluate the RV Score (Robust Value). The stocks with the highest RV Score are considered cheap and ideal to buy.
