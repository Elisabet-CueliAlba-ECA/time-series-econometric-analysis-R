# Time Series Econometrics & Forecasting (R)

## Project Overview
This repository contains a collection of advanced econometric models and time series forecasting techniques developed in R. Through various empirical datasets and synthetic data, the projects implement state-space representations, maximum likelihood estimations, and exponential smoothing methods with cross-validation.

## Tools & Libraries
* **Language:** R
* **Key Libraries:**
  * `forecast` and `fpp2`: Used for modeling, seasonal decomposition, and predictive evaluation of time series.
  * `FKF` (Fast Kalman Filter): Implemented for state estimation using the Kalman Filter.
  * `stats`: Applied for parameter optimization via Maximum Likelihood using `optim()`.

## Projects Index & Quantitative Analysis

### 1. SSARMA(1,2) Modeling and Kalman Filter
* **Objective:** Manual implementation of the state-space representation for an ARMA(1,2) model using synthetic data.
* **Quantitative Analysis:**
  * Estimated parameters by calculating the Hessian matrix and optimizing the negative log-likelihood function with `optim()`.
  * Constructed 95% confidence intervals to evaluate the statistical significance of the estimated parameters.
  * Applied the Kalman Filter (`fkf()`) to obtain filtered state estimates, and the Kalman Smoother (`fks()`) to integrate information across the entire sample.
  * Conducted diagnostic checks using Q-Q plots and ACF of residuals, identifying heavy tails characteristic of a T-Student distribution.

### 2. Forecasting Performance of Non-Seasonal Methods
* **Objective:** Evaluated and compared the predictive capacity of non-seasonal forecasting methods applied to the `livestock` time series.
* **Quantitative Analysis:**
  * Split the sample to isolate the 2001-2005 period as a test set for measuring forecast accuracy.
  * Estimated four models: Simple Exponential Smoothing (SES), Holt's method, Damped Holt's method, and Damped Holt with an exponential trend.
  * Assessed predictive accuracy by comparing key metrics such as RMSE, MAE, and MAPE across the forecasts.
  * Concluded that Holt's and Exponential Damped Holt methods provided the best fit for the real data trends.

### 3. Seasonal Exponential Smoothing and Holt-Winters
* **Objective:** Advanced modeling of the `austourists` time series by addressing its strong seasonal component.
* **Quantitative Analysis:**
  * Automatically estimated the state space to generate an optimal ETS(M,A,M) model (Multiplicative Error, Additive Trend, Multiplicative Seasonality).
  * Manually applied additive and multiplicative Holt-Winters methods to compute one-to-eight-ahead forecasts.
  * Decomposed and visually compared the level, slope, and seasonal components extracted by both forecasting approaches.

### 4. Evaluation of MAM Models and Cross-Validation
* **Objective:** Fitted specific ETS models and rigorously measured out-of-sample forecast errors using the `ausbeer` production dataset.
* **Quantitative Analysis:**
  * Estimated and directly compared the in-sample performance of an ETS(M,A,M) model against an ETS(A,A,A) approach.
  * Programmed a **Cross-Validation** algorithm using an increasing rolling training set via loops.
  * Dynamically calculated one-step-ahead forecasts and evaluated their respective squared errors over time.
  * Achieved an out-of-sample Root Mean Squared Forecast Error (RMSFE) of 13.98, validating the model's predictive robustness.

---
*Developed by **Elisabet Cueli Alba** — Specializing in Quantitative Finance & Time Series Econometrics.*
