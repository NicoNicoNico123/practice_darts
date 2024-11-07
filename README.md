# Stock Price Prediction Using Temporal Fusion Transformer

This notebook provides an in-depth exploration of stock price prediction, focusing on solving time series problems using the Temporal Fusion Transformer (TFT) architecture from the Darts library. As I continue learning about machine learning, I have chosen to tackle the problem of predicting stock prices. This project aims to deepen my understanding of time series forecasting techniques while incorporating various powerful libraries to enhance the analytical process.

## Notebook Overview

This project encapsulates the steps involved in preparing, modeling, and visualizing stock price data, with an emphasis on building robust forecasting models that incorporate both historical and forward-looking features for more reliable predictions.

## Core Libraries Utilized:
- **Datasets**: Streamlines data ingestion and manipulation.
- **u8darts[all]**: Provides an end-to-end framework for sophisticated time series analysis.
- **pandas-market-calendars**: Ensures accurate handling of trading days by integrating NYSE calendar data.
- **Pygwalker**: Enhances data exploration and visualization through interactive, intuitive plots.

## Key Notebook Components:

### 1. Data Preparation
- **Data Source**: Loads and processes stock data stored in a Parquet file.
- **Business Day Handling**: Integrates NYSE trading calendar for accurate day counting.
- **Time Series Conversion**: Transforms financial data into Darts TimeSeries objects for seamless integration with the Darts library.
- **Data Splitting Strategy**: Implements a 70/30 training-validation split for robust model training.

### 2. Feature Engineering
Utilizes distinct feature categories for comprehensive model inputs:
- **Target Variable**: Stock closing prices.
- **Past Covariates**: Technical indicators (e.g., money flow index, ultimate oscillator), volume, market capitalization, and treasury yields.
- **Future Covariates**: Earnings metrics such as EPS, forecasts, and consensus data to capture future potential impacts.

### 3. Model Architecture
The TFT model is fine-tuned for effective time series forecasting:
- **Input Specifications**: 7-day input window with a 1-day forecast horizon.
- **Model Configuration**: 64 hidden units, 2 LSTM layers, 4 attention heads, and a dropout rate of 0.2.
- **Quantile Regression**: Produces probabilistic forecasts for richer insights.

### 4. Training and Evaluation
- **Early Stopping**: Safeguards against overfitting and improves model generalization.
- **Evaluation Metrics**: Assesses model performance using MAPE, SMAPE, and MAE.
- **Probabilistic Forecasts**: Generates results with confidence intervals for better decision-making.
- **Visualization**: Displays predicted values with uncertainty bands and highlights the train-validation split.

### 5. Interactive Visualizations
- Comprehensive plots illustrate training data, validation data, median forecasts, and the 5th-95th percentile range.
- Separate visualizations for each stock symbol ensure detailed analysis and understanding.