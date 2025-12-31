# Hourly-Electricity-Demand-Forecasting---Baseline-Analysis

## Project Overview 

This project investigated the short-horizon (1hr ahead) electricty demand forecasting using historical hourly data downloaded from Kaggle 

The primary goals of this project included:
- Establishing Strong Baseline Benchmarks
- Understand the limtation of forecasting with respect to the actual forecasting horizon
- Demonstrate Time-Series modelling discipline

## Motivation
In energy forecasting (at the short time horizon) naive baselines can outperfom complex models.

This project was started to investigate that. 
- The effect of persistance was quantified
- Multiple Classical Benchmarks were tested
- Data Leakage was avoided with rigour
- Results were interpretated in a physically and statically meaningful way

## Dataset
  - Kaggle (https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption/data?select=PJM_Load_hourly.csv)
  - Time Period - 1998 to 2002
  - Frequncy - Hourly
  - Target - Electricity Load (MW)

  Data Preprocessing steps included:
  - Continuity and DST checks
  - Interpolation for missing data
  - Train/Validation Seperation


## Methods Implemented

  ### Baseline Models
- Persistance
- Same Hour Yesterday (24hr lag)
- Same Hour Last Week (168hr lag)
- Global Mean Baseline
- Simple Moving Average (6hr, 12hr, 24hr, 168hr)

### Statistical Time-Series Models
- Simple Exponential Smoothing (SES)
- Holt's Linear trend method
- Seasonal Exponential Smoothing (Daily and Weekly)

### Key Results & Insights
- Persistance baseline was the most dominant, with the lowes MAE and RMSE values when it came to forecasting for 1hr ahead, it outperformed all seasonal and smoothing-based modelling.
- At short horizons, the lagged baselines performed much worse then expected at short horizons.
- Statistical smoothing models (i.e. SES, Holt, and Holt-Winters) were unable to outperfrom persistance
- Results highlight how strong short term correlation is in electricity demand

### Limitations
- No external/extra data i.e weather, temperatute etc to supplement model development
- Forecast horizon was restricted to 1hr ahead
- Project focused on baseline benchmarking and statistical models not machine learning or production deployment


### Future Work
- Reformulate the task as a day head forecasting problem, where seasonal and ML models will be more competatitve
- Feature based regression will be introduced

### Tools and Libraries Used
- Python
-   Pandas
-   NumPy
-   Matplotlib
-   Statsmodels
-   Scikit-Learn
