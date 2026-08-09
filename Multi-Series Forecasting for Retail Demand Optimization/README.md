# Multi-Series Forecasting for Retail Demand Optimization

## 📌 Overview

This project focuses on forecasting daily retail demand across multiple related time series defined by store-item combinations.

The objective is to predict future product demand by capturing:

- Store-specific demand patterns
- Item-specific demand patterns
- Weekly and yearly seasonality
- Temporal trends
- Historical demand dependencies
- Short-term demand fluctuations

A LightGBM regression model is trained using time-series features and used to generate 90-day forecasts for multiple store-item combinations.

---

## 🎯 Problem Statement

Retail businesses need accurate demand forecasts to make better inventory and supply chain decisions.

This project uses historical daily sales data from multiple stores and items to forecast future demand.

The dataset contains:

- **10 stores**
- **50 items**
- **500 store-item time series**
- Approximately **5 years of historical daily sales**
- **90 days of future demand to forecast**

The final system generates **45,000 predictions** for the 90-day forecasting period.

---

## 📊 Dataset

The dataset contains the following columns:

### Training Data

| Column | Description |
|--------|-------------|
| `date` | Date of the observation |
| `store` | Store identifier |
| `item` | Item identifier |
| `sales` | Number of units sold |

### Test Data

| Column | Description |
|--------|-------------|
| `id` | Unique row identifier |
| `date` | Future date |
| `store` | Store identifier |
| `item` | Item identifier |

The training data covers daily sales from **2013 to 2017**, while the test period covers **90 future days in 2018**.

---

## 🔍 Exploratory Data Analysis

The dataset was analyzed to understand:

- Overall sales distribution
- Store-level demand
- Item-level demand
- Daily demand trends
- Weekly seasonality
- Monthly seasonality
- Yearly trends
- Store-item demand differences

The analysis showed that demand varies across stores and items and exhibits recurring temporal patterns.

---

## ⚙️ Feature Engineering

Several time-series features were created to help the model capture historical demand patterns.

### Calendar Features

- Year
- Month
- Day of week
- Day of year
- Week of year
- Weekend indicator

### Lag Features

Historical sales were used to create:

- `lag_1`
- `lag_7`
- `lag_14`
- `lag_28`
- `lag_365`

These features capture short-term, weekly, monthly, and yearly demand patterns.

### Rolling Features

Rolling statistics were calculated using only historical observations:

- 7-day rolling mean
- 14-day rolling mean
- 28-day rolling mean
- 60-day rolling mean
- 90-day rolling mean
- 7-day rolling median
- 28-day rolling median
- 7-day rolling standard deviation
- 28-day rolling standard deviation

A shift operation was applied before calculating rolling statistics to prevent data leakage.

---

## 🤖 Modeling

### Baseline

A seasonal-naive forecasting approach was used as the baseline:

> Today's demand = demand from the same store-item combination 7 days earlier.

### Machine Learning Model

A **LightGBM Regressor** was trained using the engineered time-series features.

The model was selected because it:

- Handles large tabular datasets efficiently
- Captures nonlinear relationships
- Handles interactions between features
- Provides feature importance
- Scales well to large datasets

---

## 🧪 Validation Strategy

Random train-test splitting was avoided because it can cause temporal data leakage.

Instead, a chronological split was used:

```text
2013 ───────────────── 2017-09-30 | 2017-10-01 ───────── 2017-12-31
              Training              |        Validation
