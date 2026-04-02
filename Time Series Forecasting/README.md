# Household Energy Consumption Forecasting

This project develops a time series forecasting workflow for household appliance energy consumption using the `energydata_complete.csv` dataset. The work covers data preparation, exploratory analysis, feature engineering, model development, and model comparison using both a statistical forecasting approach and a deep learning approach.

The objective of the project is to predict appliance energy usage and determine which modelling approach is more suitable for this time series problem.

## Summary

In this project, I:

- analysed time-based patterns in household energy consumption
- engineered cyclical time features to better represent repeating temporal behaviour
- built and evaluated both ARIMA and LSTM forecasting models
- compared model performance using RMSE, MAE, and R²
- selected LSTM as the final model based on stronger predictive performance

## Business and Technical Context

Energy consumption forecasting is useful for understanding usage patterns, improving planning, and supporting more efficient energy management. In this dataset, appliance usage changes over time and is influenced by behavioural and environmental factors. This makes the task a suitable example of time series modelling with both traditional and deep learning methods.

## Dataset

The dataset used in this project is `energydata_complete.csv`.

Key points:

- the prediction target is `Appliances`
- the `date` column is converted to datetime format and used as the time index
- selected explanatory variables include `lights`, `T_out`, `Press_mm_hg`, and time-derived features
- unnecessary random variables such as `rv1` and `rv2` are removed before modelling

## Methodology

### Data Preparation
The dataset is loaded into Pandas, and the `date` column is converted into a datetime index for time series analysis. The target variable and relevant input features are then prepared for modelling.

### Exploratory Data Analysis
The analysis examines:

- the time series behaviour of `Appliances`
- average appliance usage by hour of day
- average appliance usage by day of week
- autocorrelation patterns
- the distribution and descriptive statistics of the target variable

This step helps identify trend, seasonality, and recurring behaviour in the data.

### Feature Engineering
To better represent cyclical temporal structure, the following features are created:

- `hour_sin`
- `hour_cos`
- `day_sin`
- `day_cos`

These features improve the representation of repeating hourly and weekly patterns compared with raw time values alone.

### Preprocessing
The data is split into training and testing sets using a time-based split. Numeric variables are scaled using `MinMaxScaler`, and sequence windows are prepared for the LSTM model.

## Models

### ARIMA / ARIMAX
ARIMA is used as a statistical baseline model. In this project, exogenous variables are included, making the model closer to an ARIMAX or SARIMAX configuration. This model is useful for capturing linear time-dependent relationships and providing an interpretable baseline.

### LSTM
LSTM is used as a deep learning sequence model. It is designed to capture more complex temporal dependencies and non-linear patterns in sequential data. In this project, the LSTM model is trained on rolling input sequences of 144 time steps.

## Evaluation

The models are compared using:

- RMSE
- MAE
- R²

These metrics are used to assess both prediction accuracy and overall explanatory performance.

## Results

The comparison showed that LSTM outperformed ARIMA overall.

Main findings:

- ARIMA captured the general trend reasonably well
- ARIMA predictions were smoother and less responsive to sudden changes
- LSTM was better at learning complex sequential patterns
- LSTM achieved lower RMSE and MAE and a higher R² score

Based on these results, LSTM was selected as the final model.

## Why the Final Model Was Chosen

LSTM was chosen because the energy consumption series contains more complex temporal behaviour than a purely linear model can easily capture. Compared with ARIMA, LSTM better handled changing usage patterns and produced more accurate forecasts.

ARIMA was still a useful baseline because it provided a simpler and more interpretable comparison point.

## Skills Demonstrated

This project demonstrates the following skills:

- time series analysis
- data cleaning and preprocessing
- exploratory data analysis
- feature engineering for cyclical variables
- statistical forecasting
- deep learning for sequential data
- model evaluation and comparison
- communicating model choice based on evidence

## Project Files

- `a1906146_Lin chung Ju_assign2.ipynb` — full notebook containing the workflow
- `energydata_complete.csv` — dataset used in the analysis
- `README.md` — project summary

## The Visual charts

Please open the jupyter notebook file Time_Series_Forecasting.ipynb to see the Visual charts
