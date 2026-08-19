# YouTube Analytics Prediction

Predictive analytics project on YouTube video performance data — from exploratory data analysis to a machine learning model forecasting video views using early (day 1-7) performance signals.

## Project Goal

Predict a video's total view count using metadata and its performance during the first 7 days after publication, in order to support early content performance forecasting.

## Datasets

| File | Description |
|---|---|
| Aggregated_Metrics_By_Country_And_Subscriber_Status | Video performance broken down by country and audience type (subscribers vs. non-subscribers) |
| Aggregated_Metrics_By_Video | Core performance indicators per video, including monetization data |
| All_Comments_Final | All comments posted on the videos |
| Video_Performance_Over_Time | Daily video performance evolution since publication |

## Methodology

1. **Data cleaning** — removed aggregate "Total" row, fixed corrupted column headers, stripped whitespace from video IDs, standardized date formats
2. **Exploratory Data Analysis** — view distribution, top videos, correlations, subscriber vs non-subscriber engagement
3. **Feature engineering** — built a 222-video dataset combining publish metadata, video length, country reach, and day 1-7 performance (views, likes, comments, average view percentage)
4. **Modeling** — trained Linear Regression and Random Forest models on `log(views)`

## Key Finding: Data Leakage

A first model using all available features (including total country reach and total comment count) reached R² = 0.93 — but these features are only known *after* a video's full lifecycle, making the model unusable for early prediction.

The corrected model, using only features available at day 7, achieves a more realistic and honest **R² = 0.63**, driven mainly by subscribed audience share and early views/likes.

| | Linear Regression | Random Forest |
|---|---|---|
| MAE | 0.687 | 0.456 |
| RMSE | 0.881 | 0.696 |
| R² | 0.413 | 0.634 |

## Repository Structure

```
youtube-analytics-prediction/
│
├── raw/                              # Original CSV datasets
├── data/processed/                   # Cleaned & joined dataset
├── models/                           # Saved trained model (best_model_v2.pkl)
├── reports/                          # Result exports (feature importance, metrics)
├── YouTube_Analytics_Prediction.ipynb  # Full analysis notebook (data prep → EDA → modeling)
├── Rapport_Projet_YouTube.pdf        # Full project report (French)
└── README.md
```

## Tech Stack

- Language: Python 3.x
- Data Analysis: pandas, numpy
- Visualization: matplotlib
- Modeling: scikit-learn
- Notebook environment: Jupyter

## Getting Started

```bash
git clone https://github.com/palycode25/Youtube-analytics-prediction.git
cd Youtube-analytics-prediction
pip install pandas numpy scikit-learn joblib matplotlib jupyter
jupyter notebook YouTube_Analytics_Prediction.ipynb
```

## Status

Baseline model complete. Next steps: hyperparameter tuning, cross-validation, comment sentiment features, pure time-series approach.

## License

TBD
