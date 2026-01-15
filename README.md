FINANCIAL MARKET TREND & SECTOR ANALYSIS
========================================

PROJECT OVERVIEW
----------------
This project analyzes the correlation and relative risk (Beta) of major Indian NSE sectors (Bank, IT, Auto, Pharma) against the benchmark Nifty 50 Index.

Goal: To identify defensive vs. aggressive sectors and visualize market sensitivity for portfolio allocation strategies.

TECH STACK
----------
* Python (yfinance): Automated extraction of 2 years of OHLCV market data.
* Excel: Statistical computation of Daily Returns and Volatility.
* Power BI: Interactive dashboarding for Trend Analysis and Risk visualization.


VISUAL ANALYSIS
---------------

1. BANKING SECTOR: HIGH BETA & STRONG CORRELATION
* **Left Chart:** Shows the close tracking between Nifty 50 and Bank Nifty.
* **Right Chart:** The tight diagonal clustering in the scatter plot confirms a strong positive correlation (High Beta).
![Bank Dashboard](Trend_Analysis_Bank.PNG)

2. IT SECTOR: DIVERGENCE ANALYSIS
* **Left Chart:** Highlights periods where the IT sector trends decouple from the broader market.
* **Right Chart:** The scatter plot reveals a lower correlation coefficient, indicating potential hedging properties.
![IT Dashboard](Trend_Analysis_IT.PNG)

3. AUTO SECTOR: CYCLICAL SENSITIVITY
* **Analysis:** An examination of the Auto sector's volatility relative to market benchmarks over the 2-year period.
![Auto Dashboard](Trend_Analysis_Auto.PNG)

4. PHARMA SECTOR: DEFENSIVE ANALYSIS
* **Analysis:** Pharma often acts as a defensive sector. The scatter plot below visualizes its lower sensitivity to market crashes compared to Banking.
![Pharma Dashboard](Trend_Analysis_Pharma.PNG)


HOW TO RUN
----------
1. Run Data_Fetcher.py to pull the latest NSE data.
2. Open Market_Dashboard.pbix in Power BI Desktop to interact with the visualizations.
