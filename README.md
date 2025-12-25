# ARIMA–GARCH Based Financial Time Series Modeling

This project explores **ARIMA (AutoRegressive Integrated Moving Average)** and  
**GARCH (Generalized AutoRegressive Conditional Heteroskedasticity)** models applied to
financial time series data from multiple publicly traded companies.

The focus is on separating **mean dynamics** from **volatility dynamics**, understanding
stationarity, and producing **short-horizon forecasts for returns** alongside
**medium-horizon forecasts for risk**.

---

## 📈 Project Overview

Financial price series are inherently non-stationary, while **returns are typically stationary
but heteroskedastic**.

The repository files demonstrate how to:

- Transform raw price data into stationary return series
- Model **short-term mean behavior** using ARIMA
- Model **volatility clustering and risk persistence** using GARCH
- Compare competing models using information criteria (AIC)
- Generate interpretable forecasts for both **returns** and **uncertainty**

The analysis is performed on historical stock data from multiple companies to observe how
mean and volatility dynamics differ across assets and market regimes.

---

## 🔍 Methodology

### 1. Data Collection
- Historical adjusted close prices
- Multiple publicly traded companies for comparison

### 2. Preprocessing
- Log transformation of prices
- Log-differencing to obtain returns
- Aggregation to weekly frequency
- Stationarity checks (ADF test)
- Visual inspection of returns and volatility

### 3. Mean Modeling (ARIMA)
- Identification using ACF / PACF
- ARIMA model selection via AIC
- Low-order models favored to avoid overfitting
- Residual diagnostics to confirm weak mean dependence

### 4. Volatility Modeling (GARCH)
- GARCH modeling on ARIMA residuals or directly on returns
- Capture of volatility clustering and persistence
- Model comparison using AIC
- Forecasting conditional variance (volatility), not direction

### 5. Forecasting
- **ARIMA**: short-horizon (1–2 weeks) mean forecasts
- **GARCH**: medium-horizon (≈4 weeks) volatility forecasts
- Visualization using volatility cones (±2σ)

---

## 🛠 Tools & Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- Statsmodels
- arch (for GARCH modeling)

---

## 📌 Key Takeaways

- ARIMA models the **conditional mean** of returns
- GARCH models the **conditional variance** (volatility)
- Financial returns exhibit weak mean predictability
- Volatility displays strong persistence and clustering
- Forecasting risk is often more reliable than forecasting direction
- Model performance is evaluated **comparatively**, not absolutely

---

## 📄 License

This project is licensed under the MIT License.

---

## ✨ Disclaimer

This project is for educational and research purposes only and does not constitute
financial advice.
