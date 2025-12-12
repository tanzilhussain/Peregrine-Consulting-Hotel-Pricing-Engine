---

## Hotel Pricing Engine

**Peregrine Consulting × USC Kappa Theta Pi**

## Overview

The **Hotel Pricing Engine** is an AI-powered analytics project designed to predict key hotel performance metrics—**Occupancy Rate, Average Daily Rate (ADR), and RevPAR**—to support data-driven pricing and asset management decisions.

This project was developed in collaboration with **Peregrine Consulting** as part of a consulting engagement with **USC Kappa Theta Pi**, focusing on applying machine learning to real-world hotel revenue management problems.

---

## Problem Statement

Hotel asset managers rely on pricing and occupancy forecasts to maximize **RevPAR**, a core driver of hotel valuation. However, pricing decisions are influenced by many interacting factors such as location, seasonality, competition, and property characteristics.

This project answers:

* Which hotel features most influence pricing and demand?
* How accurately can we predict occupancy, ADR, and RevPAR?
* Which machine learning models perform best for hotel pricing analytics?

---

## Dataset

The dataset was manually constructed for **50 hotels in the Ginza district of Tokyo** using a combination of APIs and market research.

### Data Collection Sources

* **Google API** – hotel ratings and geographic coordinates
* **Expedia** – nightly room rates across multiple seasons
* **Google Maps** – distance to nearest train station

### Key Features

* Hotel rating
* Room rate
* Competitor density
* Distance to closest train station
* Property type (star rating)
* Average high-season rate
* Average low-season rate
* Monthly seasonality indicators

### Target Variables

* **Occupancy Rate**
* **ADR (Average Daily Rate)**
* **RevPAR (Revenue Per Available Room)**

---

## Models Evaluated

Multiple machine learning models were trained and evaluated:

* Linear & Ridge Regression
* Support Vector Regression (SVR)
* Neural Network (MLP)
* LSTM
* Random Forest
* LightGBM
* **XGBoost (Best Performing Model)**

### Evaluation Metrics

* **R²** – explained variance
* **RMSE** – prediction error magnitude
* **MAE** – average absolute error
* **MAPE** – percentage-based error

---

## Results

**XGBoost** significantly outperformed all other models:

* **R² ≈ 0.99**
* Lowest RMSE, MAE, and MAPE across all KPIs
* Strong predictive power for **ADR**
* Moderate predictability for **RevPAR**
* Occupancy was the hardest KPI to predict due to missing demand-side signals (events, tourism flows)

---

## Feature Insights

Feature importance analysis showed that:

* **Room Rate, High-Season Rate, and Rating** were the strongest drivers of ADR
* **Competitor Density and Location** influenced occupancy
* Seasonal pricing stability improves model accuracy

These insights can directly inform pricing strategy and competitive benchmarking.

---

## Sample Predictions

The model was tested on simulated hotel profiles:

* **Mid-range business hotel**
* **Luxury premium hotel**

For each, the model generated realistic predictions for:

* Occupancy Rate
* Monthly ADR
* Monthly RevPAR

This demonstrates how the engine can be used for **scenario testing** and pricing experimentation.

---

## Technology Stack

* **Python**
* pandas, NumPy
* scikit-learn
* XGBoost
* Seaborn & Matplotlib
* Jupyter Notebook

---

## Repository Structure

```
├── data/                 # Raw and cleaned datasets
├── notebooks/            # EDA, modeling, and evaluation notebooks
├── models/               # Trained model artifacts
├── visualizations/       # Plots and charts
└── README.md
```

---

## Limitations

* Small dataset size (50 hotels)
* No real-time demand data (events, tourism inflow)
* Single time snapshot rather than historical time series

---

## Future Work

* Expand dataset to include more hotels
* Incorporate historical pricing and occupancy trends
* Add external demand signals (events, seasonality indices)
* Deploy as an interactive pricing decision dashboard

---
