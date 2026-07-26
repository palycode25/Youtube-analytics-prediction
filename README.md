# YouTube Analytics Prediction

Predictive analytics project on YouTube video performance data — from exploratory data analysis to a machine learning model forecasting video performance (views, engagement, or subscriber growth).

## Project Goal

Build a predictive model that estimates future video performance metrics based on historical YouTube Analytics data, in order to support content and channel growth strategy.

Target variable, prediction horizon, and success metrics are defined in the scoping phase (see `/docs/scope.md`).

## Datasets

| File | Description |
|---|---|
| Aggregated_Metrics_By_Country_And_Subscriber_Status | Video performance broken down by country and audience type (subscribers vs. non-subscribers) |
| Aggregated_Metrics_By_Video | Core performance indicators per video |
| All_Comments_Final | All comments posted on the videos |
| Video_Performance_Over_Time | Video performance evolution over time |

## Project Phases

This project is tracked in Jira, structured as follows:

1. Project Scoping — define target variable, prediction horizon, success metrics
2. Exploratory Data Analysis (EDA) — audit sources, map relationships, statistical exploration
3. Data Preparation — cleaning, joining, feature engineering, train/test split
4. Modeling — baseline model, advanced models (Random Forest, XGBoost, time-series)
5. Optimization — feature selection, hyperparameter tuning, cross-validation
6. Delivery — interpretation, insights, final dashboard/report

## Repository Structure

```
youtube-analytics-prediction/
│
├── data/
│   ├── raw/              # Original, unmodified datasets
│   └── processed/        # Cleaned & joined datasets ready for modeling
│
├── notebooks/            # Jupyter notebooks for EDA and experimentation
│
├── src/
│   ├── data_prep.py      # Cleaning & feature engineering scripts
│   ├── train_model.py    # Model training pipeline
│   └── evaluate.py       # Model evaluation & metrics
│
├── models/                # Saved trained models
│
├── reports/                # Final analysis, visualizations, and results
│
├── docs/
│   └── scope.md          # Project scoping document
│
├── requirements.txt
└── README.md
```

## Tech Stack

- Language: Python 3.x
- Data Analysis: pandas, numpy
- Visualization: matplotlib, seaborn
- Modeling: scikit-learn, XGBoost
- Notebook environment: Jupyter

## Getting Started

```bash
git clone https://github.com/<your-username>/youtube-analytics-prediction.git
cd youtube-analytics-prediction
pip install -r requirements.txt
```

## Status

Project in progress — currently in the Scoping / EDA phase.

## Project Management

Tasks and progress are tracked via Jira, with Epics mapped to each project phase above.

## License

TBD
