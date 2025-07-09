# Time Series Forecasting: Monthly Car Manufacturing in Spain

This project applies the Box-Jenkins methodology to forecast monthly passenger car production in Spain, using ARIMA models enhanced with outlier treatment and calendar effects correction. The workflow emphasizes rigorous validation, interpretability, and practical forecasting accuracy.

---

## 📄 Overview

The aim is to deliver accurate, interpretable forecasts by systematically addressing real-world challenges such as seasonality, calendar irregularities, and outliers—ensuring robust model validation and actionable results for industrial planning.

---

## 🗂️ Dataset

- **Source:** Ministerio de Industria, Energía y Turismo (Spain)
- **Variable:** Monthly passenger car production (`TURISMOS`)
- **Period:** 1994 onward
- **Frequency:** Monthly

The dataset is provided in `.dat` format.

---

## 🧪 Methodology

The modeling process follows these steps:

1. **Stationarity Transformation**
   - Log transform to stabilize variance.
   - Regular and seasonal differencing to remove trend and seasonality.

2. **Model Identification**
   - Analyze ACF and PACF plots.
   - Candidate models:  
     - ARIMA(0,1,1)(1,1,0)[12]  
     - ARIMA(0,1,1)(0,1,1)[12]

3. **Estimation**
   - Parameters estimated via maximum likelihood (R).
   - Model selection based on AIC/BIC criteria.

4. **Validation**
   - Residual diagnostics: normality, independence, and homoscedasticity.
   - Ljung-Box test for autocorrelation.
   - Out-of-sample validation (last 12 months).

5. **Calendar Effects Correction**
   - Adjust for variable working days and holidays.
   - Integrate calendar regressors.

6. **Outlier Detection**
   - Automatically identify additive, level shift, and temporary change outliers.
   - Re-estimate models excluding anomalies.

7. **Forecasting**
   - Produce 12-month ahead forecasts with confidence intervals.

---

## 🔍 Key Results

- **Model Selection:**  
  - ARIMA(0,1,1)(0,1,1)[12] chosen for final forecasting after outlier and calendar effect adjustments.

- **Residuals:**  
  - Adjustments improved independence, normality, and reduced forecast errors.

- **Accuracy:**  
  - Lower MAE, RMSE, and MAPE in the adjusted model.

| Metric   | Original Model | Adjusted Model |
|----------|----------------|----------------|
| MAE      | 17.95          | 16.89          |
| MAPE     | 10.32%         | 9.04%          |
| RMSE     | 22.54          | 21.57          |
| AIC      | -326.25        | -621.27        |

---

## 📂 Repository Structure

```
/ProyectoHPC.zip        → Contains all scripts, the PDF report, and the dataset
  ├── *.Rmd             → R Markdown scripts for estimation, validation, and forecasting
  ├── *.pdf             → Final project report
  └── *.dat             → Original time series data
```

---

## 💡 Conclusions

- Adjusting for calendar effects and outliers significantly enhances model performance.
- Even moderate improvements in forecast accuracy can have substantial value for industrial decision-making.
- The ARIMA(0,1,1)(0,1,1)[12] model, with appropriate adjustments, proved both robust and interpretable for this time series.

---

## 📚 References

- Box, G.E.P., Jenkins, G.M., Reinsel, G.C., & Ljung, G.M. (Time Series Analysis)
- R Documentation
- Ministerio de Industria, Energía y Turismo (Spain)

---
