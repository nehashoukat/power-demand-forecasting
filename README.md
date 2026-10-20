<<<<<<< HEAD
# Great Britain Electricity Demand Forecasting

A time series forecasting project comparing statistical and deep learning models to predict hourly electricity demand in Great Britain.

## Overview

This project explores historical electricity demand patterns and evaluates different forecasting approaches, from simple seasonal baselines to statistical time series models and Long Short Term Memory (LSTM) neural networks.

The aim is to compare model performance using a consistent evaluation period and understand how different approaches perform when forecasting short-term electricity demand.

## Objectives

* Explore hourly electricity demand trends, seasonality, and temporal patterns.
* Prepare and clean time series data for forecasting.
* Establish a seasonal naive baseline.
* Develop and evaluate ARIMA, SARIMA, and LSTM forecasting models.
* Compare forecasting accuracy using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

## Models

| Model                   | Description                                                                          |
| ----------------------- | ------------------------------------------------------------------------------------ |
| Seasonal Naive          | Uses demand from the same hour of the previous day as the forecast.                  |
| ARIMA(2,0,2)            | Statistical time series model capturing autoregressive and moving-average patterns.  |
| SARIMA(1,0,1)(1,0,1,24) | Seasonal ARIMA model incorporating a 24-hour seasonal cycle.                         |
| LSTM                    | Recurrent neural network designed to learn temporal dependencies in sequential data. |

## Results

The following results are from the seven day evaluation window, comprising 168 hourly observations.

| Model                    |      MAE |     RMSE |
| ------------------------ | -------: | -------: |
| SARIMA(1,0,1)(1,0,1,24)  |   491.97 |   687.63 |
| LSTM                     |   576.55 |   760.20 |
| ARIMA(2,0,2)             |   928.99 | 1,211.94 |
| Seasonal Naive (24-hour) | 2,123.88 | 3,028.35 |

**Key finding:** SARIMA achieved the lowest MAE and RMSE in this evaluation, followed by LSTM, ARIMA, and the seasonal naive baseline.

*note:* These results use a rolling one step ahead evaluation over the final 168 observations. Actual demand becomes available as the evaluation progresses, so this is not a single forecast made seven days in advance.

## Tech Stack

* Python
* Pandas and NumPy
* Matplotlib and Seaborn
* Statsmodels
* Scikit-learn
* PyTorch
* Jupyter Notebook

## Project Structure

```text
power-demand-forecasting/
├── data/                  # Local dataset (not tracked by Git)
├── images/                # Project visualisations
├── notebooks/
│   └── 01_data_exploration_cleaned.ipynb
├── outputs/               # Saved results and charts
├── src/                   # Reusable forecasting code (planned)
├── .gitignore
├── requirements.txt
└── README.md
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd power-demand-forecasting
```

### 2. Create and activate a virtual environment

On macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Prepare the dataset

Place the required CSV file, `time_series_60min_singleindex.csv`, inside the `data/` directory.

This project uses the hourly electricity time series dataset from Open Power System Data (OPSD).The dataset is not included in this repository at present. 

### 5. Run the notebook

Open Jupyter Notebook or VS Code, then run:

```text
notebooks/01_data_exploration_cleaned.ipynb
```

Run the notebook cells in order. Results depend on having the required dataset and compatible dependencies installed.

## Future Improvements

* Refactor reusable forecasting functions into the `src/` directory.
* Add automated evaluation tests and improve reproducibility.
* Build an interactive dashboard using Streamlit.
* Develop a forecasting API using FastAPI.
* Containerise the application with Docker.
* Explore monitoring and model performance over time.

## Project Status

The initial exploratory analysis and model comparison are complete. Application development, code modularisation, and deployment are planned next.
=======
# power-demand-forecasting
Hourly electricity demand forecasting using statistical time series models and LSTM neural networks.
>>>>>>> 2405dcd0331f942af1a03f0f1e203246e75c4f50
