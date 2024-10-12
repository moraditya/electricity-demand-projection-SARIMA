# Electricity Demand Projection Project

This repository contains a time series forecasting project that predicts electricity consumption using SARIMA models. The goal of this project is to model historical electricity demand and forecast future demand based on the historical data.

## Table of Contents
- [Project Overview](#project-overview)
- [Directory Structure](#directory-structure)
- [Data Source](#data-source)
- [Installation](#installation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling](#modeling)
  - [SARIMA Model](#sarima-model)
  - [Evaluation](#evaluation)
  - [Forecasting](#forecasting)
- [Dynamic Forecasting using a Graphical User Interface](#dynamic-forecasting-using-a-gui)
- [Conclusion](#conclusion)
- [License](#license)

## Project Overview

The aim of this project is to forecast electricity consumption using historical data and time series modeling techniques. The model is built using the **Seasonal ARIMA (SARIMA)** model, which takes into account both the trend and seasonality in electricity consumption.

## Directory Structure

The repository is organized as follows:
1. Data: contains the electricity consumption dataset
2. Model: contains the SARIMA model along with the GUI that allows users to input the number of months they would like to see forecasted.



## Data Source

The dataset used for this project contains electricity consumption data in Trillion Watts (TW) on a monthly basis. The data is processed for missing values and converted into a time series format.

## Installation

To run the project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/moraditya/electricity-demand-projection-SARIMA.git
    ```

2. Navigate to the project directory:
    ```bash
    cd electricity-demand-projection-SARIMA
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Make sure the data is available in the `/data` folder.

## Exploratory Data Analysis (EDA)

The EDA step includes data cleaning, handling missing values, and basic visualization of electricity consumption over time.

1. **Data Cleaning:** Removed NaN values and ensured that the date column is in `datetime` format.
2. **Visualization:** A plot of the electricity consumption shows both upward trends and seasonal patterns.
   
![image](https://github.com/user-attachments/assets/59836d29-95f7-4814-9a62-d42984e9b7c5)


3. **Stationarity Test:** The Augmented Dickey-Fuller test indicates that the time series is non-stationary, and first-order differencing is applied to make it stationary.

![image](https://github.com/user-attachments/assets/4cc8136c-f28b-4acb-82ed-77bceddab22c)


## Modeling

### SARIMA Model

The Seasonal ARIMA (SARIMA) model is used to model the seasonality and trend in the electricity consumption data.

- **Seasonal decomposition** was used to identify the trend, seasonality, and residual components.
- **Auto-ARIMA** was employed to automatically select the optimal SARIMA parameters.
- The model is evaluated using train and test data (24 months of test data).

### Evaluation

Model performance was evaluated using various metrics:
- **RMSE** (Root Mean Squared Error): 4.70
- **MAPE** (Mean Absolute Percentage Error): 1.72%
- **RMSPE** (Root Mean Squared Percentage Error): 0.021%


### Forecasting

The SARIMA model was used to forecast electricity consumption for the next two years. The forecast includes confidence intervals to represent the uncertainty in predictions.


## Dynamic Forecasting Using a GUI

A simple Tkinter-based GUI was created to allow dynamic forecasting for any number of months. Users can specify the number of months to forecast, and the application will generate the forecast along with confidence intervals.

1. **Input:** Number of months to forecast.
2. **Output:** Forecasted electricity consumption with confidence intervals plotted on the chart.

![image](https://github.com/user-attachments/assets/bf93177d-c7b2-431f-8e4a-006a01c9c4d6)


## Conclusion

The SARIMA model provides a robust method for forecasting electricity demand, accounting for both trend and seasonality. The project demonstrates time series analysis using Python and highlights the importance of stationarity and model selection in time series forecasting.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE.txt) file for details.
