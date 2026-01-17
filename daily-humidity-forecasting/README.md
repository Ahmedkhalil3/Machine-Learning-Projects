# Daily Humidity Forecasting Using Time Series Models

## Overview

This project focuses on forecasting daily humidity using classical time-series modeling techniques. The goal is to analyze temporal patterns, build baseline and advanced models, and evaluate their performance using proper walk-forward validation.

The project demonstrates a complete time-series workflow, from exploratory data analysis to model comparison.

---

## Dataset

* **Type:** Daily climate time series
* **Target variable:** Humidity
* **Number of observations:** ~1,460 days
* **Frequency:** Daily
* **Missing values:** None

The dataset is clean and regularly sampled, making it suitable for time-series forecasting without extensive preprocessing.

---

## Methodology

### Exploratory Data Analysis (EDA)

* Time-series visualization
* Distribution analysis
* Rolling statistics (weekly and monthly)
* Autocorrelation (ACF) and Partial Autocorrelation (PACF)

### Baseline Model

* **Autoregressive (AR) model** with 16 lags
* Evaluated using **walk-forward validation**
* Served as a strong baseline for short-term dependency modeling

### ARIMA Model

* Grid search over ARIMA hyperparameters on training data
* Best model identified as **ARIMA(4,0,2)**
* Final evaluation performed using **walk-forward validation**

---

## Model Evaluation

Models were evaluated using:

* Walk-forward validation (one-step-ahead forecasting)
* Mean Absolute Error (MAE)
* Visual comparison of predicted vs actual values

The ARIMA(4,0,2) model demonstrated improved performance over the AR(16) baseline by better capturing residual autocorrelation and responding more effectively to changes in the series.

---

## Results

* ARIMA(4,0,2) achieved lower MAE than the AR(16) model
* Improved tracking of peaks and troughs
* More stable and smoother forecasts
* No evidence of systematic bias

---

## Conclusion

This project highlights the importance of:

* Proper exploratory analysis in time-series data
* Establishing a strong baseline model
* Using walk-forward validation for fair evaluation
* Incremental model improvement

The final ARIMA model provides a good balance between interpretability and forecasting accuracy for daily humidity data.

---

## Tools & Libraries

* Python
* pandas
* matplotlib
* statsmodels
* scikit-learn
