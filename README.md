# Electricity-Power-Load-Forecasting

Overview

This project focuses on forecasting household electrical power consumption using statistical, machine learning, and deep learning techniques. The objective was to compare the performance of ARIMA, XGBoost, and LSTM models in predicting Global Active Power consumption and identify the most accurate forecasting approach.

Problem Statement

Accurate electricity demand forecasting is essential for efficient power generation, grid stability, and energy management. Traditional statistical models often struggle to capture complex consumption patterns, while machine learning and deep learning models can leverage temporal and historical information to improve forecasting accuracy.

This project compares three forecasting approaches to determine the most effective model for short-term household power load prediction.

Dataset
Dataset: Household Power Consumption Dataset
Source: UCI Machine Learning Repository
Records: 2.07+ million observations
Time Frequency: 1-minute intervals
Time Span: Approximately 47 months
Target Variable
Global Active Power (kilowatts)
Features Used
Date
Time
Global Active Power
Global Reactive Power
Voltage
Global Intensity
Sub-metering 1
Sub-metering 2
Sub-metering 3
Project Workflow
1. Data Preprocessing
Combined Date and Time into a single datetime column.
Converted numerical columns to appropriate data types.
Handled missing values.
Sorted records chronologically.
Resampled data to 30-minute intervals for ARIMA to reduce noise.
2. Feature Engineering

Created temporal features:

Hour
Day of Week
Month
Quarter
Weekend Indicator

Created lag features:

Previous 1 interval power consumption (Lag 1)
Previous 2 interval power consumption (Lag 2)

Included:

Global Intensity

These engineered features helped capture seasonality, daily consumption patterns, and short-term dependencies.

3. Models Implemented
ARIMA
Classical time-series forecasting model.
Captures trend and autocorrelation.
Used as the baseline forecasting model.
XGBoost
Gradient Boosting regression model.
Utilized engineered temporal and lag features.
Hyperparameters optimized using GridSearchCV.
LSTM
Deep learning model designed for sequential time-series data.
Learned temporal dependencies from historical observations.
Trained for 10 epochs.
Model Evaluation

Performance was evaluated using Root Mean Squared Error (RMSE).

Model	RMSE
ARIMA	0.9616
XGBoost	0.0340
LSTM	0.5287
Results
XGBoost achieved the best forecasting performance, significantly outperforming ARIMA and LSTM.
Lag-based and temporal feature engineering enabled XGBoost to capture nonlinear consumption patterns effectively.
ARIMA provided a useful statistical baseline but was less effective for complex variations.
LSTM captured sequential dependencies but underperformed due to limited training epochs and model tuning.
Technologies Used
Python
Pandas
NumPy
Matplotlib
Scikit-learn
XGBoost
TensorFlow / Keras
Statsmodels
GridSearchCV
Key Skills Demonstrated
Time Series Forecasting
Feature Engineering
Data Preprocessing
Machine Learning
Deep Learning
Statistical Modeling
Hyperparameter Tuning
Model Evaluation
Forecast Accuracy Comparison
Repository Structure
Power-Load-Forecasting/
│
├── data/
│   ├── household_power_consumption.csv
│
├── notebooks/
│   ├── Data_Preprocessing.ipynb
│   ├── ARIMA_Model.ipynb
│   ├── XGBoost_Model.ipynb
│   ├── LSTM_Model.ipynb
│
├── models/
│
├── results/
│   ├── Forecast_Plots/
│   ├── RMSE_Comparison.png
│
├── requirements.txt
├── README.md
└── LICENSE
Future Improvements
Implement SARIMA to better capture seasonal patterns.
Tune the LSTM architecture with additional layers and epochs.
Incorporate weather and holiday data as external features.
Explore Transformer-based forecasting models for improved long-term predictions.
Conclusion

This project demonstrates a comparative analysis of statistical, machine learning, and deep learning approaches for electrical power load forecasting. Among the evaluated models, XGBoost delivered the highest predictive accuracy (RMSE = 0.0340) by effectively leveraging engineered temporal and lag features, making it the most suitable model for this forecasting task.
