# Quantitative Finance Projects — BUISSON Antoine

This repository gathers two end-to-end **quantitative finance projects** developed to prepare for Quant Research & Quant Dev interviews.  
Each project follows a clean, reproducible Python pipeline with strong theoretical grounding and statistical validation.

---

## 📊 Project 1 — Volatility Forecasting (S&P 500)

**🎯 Goal:**  
Forecast and analyze financial market volatility using both statistical and machine learning models.

**⚙️ Methods:**  
EWM, GARCH(1,1), EGARCH, GJR-GARCH, HAR-RV, LSTM  

**📈 Evaluation:**  
Diebold–Mariano tests, RMSE/MAE metrics, and backtests on ATM straddles.  

**🧰 Stack:**  
Python (NumPy, Pandas, arch, PyTorch, Matplotlib)  

📂 Folder: 1 - Research Project  - Volatility Forecasting

---

## 💸 Project 2 — Option Pricing with Black–Scholes & Monte Carlo

**🎯 Goal:**  
Price European options and validate Monte Carlo convergence against the analytical Black–Scholes model.

**⚙️ Methods:**  
Analytical Black–Scholes formula and Monte Carlo simulation under Geometric Brownian Motion (GBM).

**📈 Validation:**  
Put–Call parity, convergence log–log slope (≈ –0.5), IC95 confidence intervals, and seed reproducibility.  

**🧰 Stack:**  
Python (NumPy, SciPy, Matplotlib, Jupyter)

📂 Folder: 2 - Research Project - Option Pricing with Black–Scholes & Monte Carlo

---

## 🧪 Environment setup

Create and activate a virtual environment, then install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
