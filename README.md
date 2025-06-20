# 📉 Dynamic Portfolio Risk Analysis with EWMA & GARCH
This project models and backtests Value at Risk (VaR) for a multi-asset portfolio of **AAPL**, **MSFT**, **SPY**, and **TLT** from **2020 to 2024**, using:

- ✅ Static (historical) volatility  
- ✅ **EWMA** (Exponentially Weighted Moving Average) volatility  
- ✅ **GARCH(1,1)** model (Generalized Autoregressive Conditional Heteroskedasticity)

---

## 🎯 Objective

To understand how portfolio risk evolves over time, and evaluate whether time-dependent models like EWMA and GARCH improve VaR prediction over static volatility. Backtesting is used to validate the reliability of each model.

---

## 📊 Methodology

1. **Data Collection**  
   - Daily adjusted closing prices from Yahoo Finance  
   - Assets: `AAPL`, `MSFT`, `SPY`, `TLT`

2. **Portfolio Construction**  
   - Equal-weighted portfolio (25% each asset)

3. **VaR Modeling**  
   - Static VaR with constant volatility  
   - EWMA VaR with λ = 0.94  
   - GARCH(1,1) VaR using the `arch` package

4. **Backtesting Techniques**  
   - **Exception Counting**  
   - **Kupiec’s Proportion of Failures (POF) Test**  
   - **Christoffersen’s Independence Test**

---

## 🧪 Results Summary

| Model     | Exception Rate | Kupiec p-value | Christoffersen p-value | Verdict    |
|-----------|----------------|----------------|-------------------------|------------|
| Static    | 5.01%          | —              | —                       | ✅ Reasonable |
| EWMA      | 6.13%          | 0.075          | 0.716                   | ✅ Pass     |
| GARCH     | —              | 0.979          | 0.463                   | ✅ Best Fit |

> ✅ **GARCH VaR** performed best, accurately modeling volatility clustering and passing both statistical tests.

---

## 📦 Tools & Libraries

- `Python`, `NumPy`, `pandas`, `yfinance`
- `matplotlib`, `seaborn`
- `arch`, `scipy.stats`

---

## 📌 Key Takeaways

- Static models are simple but fail in volatile periods.  
- EWMA captures time-varying volatility effectively.  
- GARCH models volatility dynamics **and** autocorrelation, making it highly suitable for real-world risk management.  
- Backtesting ensures **model reliability**, not just accuracy.

---

## 🔗 Connect

If you're working on risk modeling, VaR, or stress testing — let's connect and exchange insights!
LinkedIn Profile: https://www.linkedin.com/in/rayan-chatterjee-phd-513390171/
GitHub link:
