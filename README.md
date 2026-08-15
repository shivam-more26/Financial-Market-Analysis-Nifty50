# Financial Market & Sector Analysis: Nifty 50 Benchmark vs. Indian Equity Sectors

Quantitative risk, relative sensitivity (**Beta $\beta$**), linear co-movement (**Pearson Correlation $r$**), and volatility modeling of major Indian sector indices against the **Nifty 50 Index (`^NSEI`)**.

---

## 📌 Executive Summary

This project conducts an empirical quantitative analysis of major sectoral indices on the National Stock Exchange of India (NSE):
- **Bank Nifty (`^NSEBANK`)**
- **Nifty IT (`^CNXIT`)**
- **Nifty Auto (`^CNXAUTO`)**
- **Nifty Pharma (`^CNXPHARMA`)**

The objective is to quantify risk-return profiles, evaluate market sensitivity ($\beta$), identify defensive vs. aggressive sector dynamics, and provide data-driven insights for strategic asset allocation and portfolio diversification.

---

## 📊 Summary of Quantitative Findings (2-Year Horizon)

| Sector / Index | Ticker | Beta ($\beta$) | Correlation ($r$) | CAGR Return | Annual Volatility | Sharpe Ratio ($R_f=6.5\%$) | Max Drawdown | Sector Profile |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Nifty 50** | `^NSEI` | **1.000** | **1.000** | **+0.42%** | **13.41%** | -0.39 | **-15.77%** | Benchmark Index |
| **Bank Nifty** | `^NSEBANK` | **1.057** | **0.889** | **+9.06%** | **15.94%** | **0.22** | **-18.32%** | Core Growth / High Beta |
| **Nifty IT** | `^CNXIT` | **0.918** | **0.524** | **-15.09%** | **23.49%** | -0.86 | **-43.97%** | High Volatility / Hedging |
| **Nifty Auto** | `^CNXAUTO` | **1.258** | **0.817** | **+4.18%** | **20.65%** | -0.01 | **-28.23%** | Cyclical / Hyper-Sensitive |
| **Nifty Pharma**| `^CNXPHARMA` | **0.630** | **0.540** | **+8.48%** | **15.65%** | **0.18** | **-16.69%** | Low Beta / Defensive |

---

## 🔬 Quantitative Methodology & Mathematical Framework

### 1. Sector Beta ($\beta$)
Measures systemic market risk and returns sensitivity relative to the Nifty 50 benchmark:
$$\beta_i = \frac{\text{Cov}(R_i, R_m)}{\text{Var}(R_m)}$$
* **$\beta > 1.0$ (Aggressive):** Amplifies broader market movements (e.g., Auto $\beta = 1.258$, Bank $\beta = 1.057$).
* **$\beta < 1.0$ (Defensive):** Exhibits lower market sensitivity and downside protection (e.g., Pharma $\beta = 0.630$).

### 2. Pearson Correlation Coefficient ($r$)
Measures the strength and direction of linear co-movement with Nifty 50:
$$r_{i, m} = \frac{\text{Cov}(R_i, R_m)}{\sigma_i \cdot \sigma_m}$$
* **Banking ($r = 0.889$):** Tight co-movement with domestic macroeconomic liquidity.
* **IT ($r = 0.524$):** Decouples from domestic market trends due to global tech/US macro sensitivity.

### 3. Annualized Volatility ($\sigma_{ann}$)
Standard deviation of daily percentage returns scaled to standard annual trading days (252):
$$\sigma_{ann} = \sigma_{daily} \times \sqrt{252}$$

### 4. Sharpe Ratio
Evaluates risk-adjusted excess returns over the Indian 10-Year Government Bond Yield ($R_f = 6.5\%$):
$$\text{Sharpe Ratio} = \frac{\text{CAGR} - R_f}{\sigma_{ann}}$$

---

## 🔍 Sectoral Analytical Profiles

### 🏦 1. Banking Sector (`^NSEBANK`) — Market Growth Engine
* **High Beta ($\beta = 1.057$) & High Correlation ($r = 0.889$):** Moves in near lockstep with Nifty 50.
* **Role:** Primary driver of domestic market rallies; essential core holding for broad market exposure.

### 💻 2. IT Sector (`^CNXIT`) — Global Decoupling & Hedging
* **Low Correlation ($r = 0.524$) & High Volatility ($23.49\%$):** Decouples from domestic Indian indices during global macroeconomic shocks.
* **Role:** Provides portfolio diversification and hedging properties against purely domestic cyclical risk.

### 🚗 3. Auto Sector (`^CNXAUTO`) — Cyclical Sensitivity
* **Highest Beta ($\beta = 1.258$):** Hyper-sensitive to economic cycles, interest rate changes, and consumer discretionary spending.
* **Role:** Tactical satellite allocation during economic expansion phases.

### 💊 4. Pharma Sector (`^CNXPHARMA`) — Defensive Cushion
* **Lowest Beta ($\beta = 0.630$) & Low Drawdown ($-16.69\%$):** Demonstrates strong capital preservation during benchmark downturns.
* **Role:** Classic defensive shock absorber for drawdown reduction.

---

## 🛠️ Project Structure

```
Market trends and sector analysis/
│
├── Market_trends_&_sector_analysis.ipynb   # Main Jupyter Notebook (Data Pipeline, Math Models & Plots)
├── Market_Sector_Analysis.xlsx            # Refined Excel Workbook (5 Structured Sheets + Excel Formulas)
├── Market Trend & Sector Analysis.pbix    # Power BI Dashboard Report
├── Trend_Analysis_Bank.PNG                # Visual Analysis Chart: Bank Nifty vs Benchmark
├── Trend_Analysis_IT.PNG                  # Visual Analysis Chart: Nifty IT vs Benchmark
├── Trend_Analysis_Auto.PNG                # Visual Analysis Chart: Nifty Auto vs Benchmark
├── Trend_Analysis_Pharma.PNG              # Visual Analysis Chart: Nifty Pharma vs Benchmark
└── README.md                              # Project Documentation
```

---

## 🚀 How to Run & Use

### 1. Execute Jupyter Notebook
Clone the repository and launch Jupyter Notebook or Jupyter Lab:
```bash
pip install yfinance pandas numpy matplotlib seaborn scipy openpyxl
jupyter notebook Market_trends_&_sector_analysis.ipynb
```
* **Step 1:** Data is dynamically extracted from Yahoo Finance for configured lookback periods (`1y`, `2y`, `5y`).
* **Step 2:** Quantitative metrics (Beta, Volatility, Sharpe, Drawdown) are computed.
* **Step 3:** Inline Matplotlib/Seaborn visual plots are rendered (Normalized Growth, Heatmaps, Scatter Regressions, Rolling Betas).

### 2. Inspect Refined Excel Workbook
Open `Market_Sector_Analysis.xlsx` in Microsoft Excel:
* **`Executive_Summary`**: KPI summary table.
* **`Raw_Prices`**: Daily closing prices.
* **`Daily_Returns_%`**: Conditional formatted return percentages.
* **`Correlation_Matrix`**: Pearson correlation matrix.
* **`Sector_Beta_Calculations`**: Native Excel `=COVARIANCE.P() / VAR.P()` & `=CORREL()` dynamic formulas.

---

## 📦 Requirements
* **Python 3.10+**
* `yfinance`
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scipy`
* `openpyxl`
