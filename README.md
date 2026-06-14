# Agentic AI-Based EV Charging Network Optimization

## Overview

This project develops an Agentic AI framework for dynamic tariff optimization in EV charging networks using large-scale charging session data. The system predicts charging demand, recommends dynamic tariffs, and continuously evaluates pricing decisions through a monitoring and learning feedback loop.

The objective is to improve charger utilization, reduce congestion, balance demand across time periods, and support efficient EV charging infrastructure operations.

---

## Problem Statement

Traditional EV charging stations often rely on fixed-rate pricing models that fail to adapt to changing demand patterns. This can lead to:

* Peak-hour congestion
* Underutilization during off-peak periods
* Increased operational costs
* Poor user experience

This project addresses these challenges by building an Agentic AI system capable of forecasting demand, optimizing tariffs, and learning from operational outcomes.

---

## Datasets Used

### 1. ACN-Data (Adaptive Charging Network)

* Source: Caltech/JPL EV Charging Network
* Coverage: 30,000+ charging sessions
* Format: JSON (converted to tabular format)
* Purpose:

  * Session-level analysis
  * Revenue evaluation
  * Customer response monitoring

### 2. UrbanEV Dataset (ST-EVCDP)

* Location: Shenzhen, China
* Coverage:

  * 24,798 charging piles
  * 247 traffic zones
  * 5-minute interval operational data
* Purpose:

  * Demand forecasting
  * Dynamic pricing
  * Utilization analysis

---

## Project Architecture

### Demand Prediction Agent

Predicts:

* Charging demand
* Charger utilization
* Congestion probability
* Expected charging load

Models evaluated:

* Naive Persistence
* Linear Regression
* Random Forest
* XGBoost

Selected model:

* XGBoost
* R² = 0.95

---

### Tariff Pricing Agent

Generates dynamic tariffs based on predicted utilization.

Pricing strategy:

* Discount pricing for low-utilization periods
* Baseline pricing for normal demand
* Surge pricing for high-demand periods

The pricing mechanism adjusts tariffs while maintaining consumer-friendly price boundaries.

---

### Monitoring & Learning Agent

Evaluates pricing decisions using:

* Revenue performance
* Utilization improvement
* Waiting-time reduction
* Customer response behavior

The agent continuously learns the optimal pricing intensity through a feedback loop.

---

## Feature Engineering

Key engineered features include:

* Charger Utilization Rate
* Revenue per Session
* Energy Cost per kWh
* Queue Length Proxy
* Occupancy Density
* Congestion Indicators
* Temporal Features

---

## Results

### Demand Prediction Agent

| Metric                        | Value |
| ----------------------------- | ----- |
| Utilization Prediction R²     | 0.95  |
| Charging Load Prediction R²   | 0.97  |
| Congestion Prediction ROC-AUC | 0.997 |

### Dynamic Pricing Outcomes

* Revenue remained near break-even
* Off-peak demand increased
* Utilization improved across underused periods
* Consumer-friendly pricing fluctuations maintained

### Monitoring Agent Outcomes

| Metric                   | Result     |
| ------------------------ | ---------- |
| Waiting Time Reduction   | 54.46%     |
| Customer Response Rate   | +0.16%     |
| Off-Peak Uplift          | +0.45%     |
| Pricing Efficiency       | ₹14.92/kWh |
| Optimal Pricing Strength | 0.60       |

---

## Repository Structure

```text
Agentic-EV-Charging-Network-Optimization/
│
├── data/
│   ├── ACN_Data/
│   └── UrbanEV_SZ_districts/
│
├── notebooks/
│   └── Code EV.ipynb
│
├── results/
│   ├── demand_forecast.csv
│   ├── dynamic_prices.csv
│   ├── consolidated_scorecard.csv
│   └── monitoring_scorecard.csv
│
├── docs/
│   ├── Problem_Statement.pdf
│   ├── Project_Report.pdf
│   └── Project_Presentation.pdf
│
├── README.md
└── .gitignore
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-Learn
* XGBoost
* Jupyter Notebook

---

## Key Takeaways

* Dynamic pricing is more effective for balancing demand than maximizing revenue.
* Most charging zones are underutilized rather than congestion-bound.
* Off-peak discounting improves utilization with minimal revenue impact.
* Agent-based monitoring enables adaptive and self-improving pricing decisions.

---

## Author

**Velamala Pujitha**
BSMS Mathematics and Computing
Indian Institute of Technology Roorkee (IIT Roorkee)
