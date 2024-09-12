# Trading Strategy Optimization with Moving Averages and RSI

This project explores optimizing a trading strategy using technical indicators, specifically Moving Averages and Relative Strength Index (RSI), and compares it to a simple buy-and-hold strategy. The goal is to demonstrate the potential of using technical analysis to outperform the market return.

---

## Project Overview

The core idea of this project is to implement a technical trading strategy and backtest it against a buy-and-hold strategy for a selected stock. The strategy uses **moving averages** and **RSI** to generate buy/sell signals, aiming to optimize returns.

---

## Data

The dataset used in this project contains stock prices and associated market information for **[Stock name, e.g., AAPL]** over a specified time period. The key columns are:

- **Date**: Trading date.
- **Open, High, Low, Close**: Stock prices.
- **Adj Close**: Adjusted closing price.
- **Volume**: Number of shares traded.

The data is loaded from a CSV file into a Pandas DataFrame and processed accordingly.

---

## Strategy Overview

### Buy-and-Hold Strategy

The baseline strategy is the standard **buy-and-hold**, where the asset is purchased at the start of the time period and held throughout, generating a return based on the price difference from the start to the end.

### Optimized Strategy

The optimized strategy involves:
- **Moving Averages (MA5 and MA20)**: We generate buy signals when the short-term moving average (MA5) crosses above the long-term moving average (MA20) and sell signals when MA5 crosses below MA20.
- **Relative Strength Index (RSI)**: An oscillator that measures overbought (sell) and oversold (buy) conditions. We buy when the RSI is below 30 and sell when it is above 70.

---

## How I Implemented It

2. **Buy and Sell Signals**:
   - Buy signal: When MA5 crosses above MA20 and RSI is below 30 (oversold).
   - Sell signal: When MA5 crosses below MA20 or RSI is above 70 (overbought).

3. **Backtesting**:
   I backtested the strategy by calculating the **strategy returns** and comparing them to the **market returns**. Cumulative returns were plotted for both strategies.

4. **Results**:
   I visualized and compared the performance of both strategies to evaluate how the technical strategy performed against a simple buy-and-hold approach.

---

## Code Structure

All the code is contained in a single Jupyter Notebook file, which includes:

1. **Data Loading and Preprocessing**: 
   - Loading stock price data.
   - Calculating the 5-period and 20-period moving averages.
   - Computing RSI using `TA-lib`.
   - Generating buy/sell signals based on MA and RSI conditions.

2. **Strategy Backtesting**:
   - Calculating returns for both the buy-and-hold strategy and the optimized strategy.
   - Comparing cumulative returns for both strategies.

3. **Results Visualization**:
   - A plot that compares the performance of the two strategies (market vs. optimized).
  

---

## How to Run the Code

### Prerequisites:
- Install the required libraries:
  ```bash
  pip install pandas numpy matplotlib talib
