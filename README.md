# RISK-ANALYSIS-PROJECT
RISK PROJECT: TYPE (TOTAL RISK VOLITALITY)
Code 
import yfinance as yf
import numpy as np

# 1. Input
stock_ticker = input("Enter Stock Ticker: ")

# 2. Download Data - "1y" is the setting for one year
data = yf.download(stock_ticker, period="1y")['Close']

# 3. Calculate Returns
returns = data.pct_change().dropna()

# 4. Calculate Volatility
daily_vol = returns.std()
annual_vol = daily_vol * np.sqrt(252)

# 5. Output
print(f" Annualized Volatility (1 Year): {annual_vol.iloc[0]:.2%}")

OUTPUT:
Annualized Volatility for AMZN (1 Year): 31.32%
INTERPRETATION:
The annualized volatility for AMZN is 31.32%. This indicates a high-risk profile. While the stock has high growth potential, the price movements are volatile, making it more suitable for investors with a high risk tolerance who can handle large short-term price swings.
