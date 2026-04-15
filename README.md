# Flood Probability Prediction

Regression pipeline for predicting flood probability from environmental and socioeconomic risk factors. Built for the [Kaggle Playground Series S4E5](https://www.kaggle.com/competitions/playground-series-s4e5) competition.

## Overview

The dataset contains 1.1M training samples with 20 integer-valued features representing factors such as monsoon intensity, deforestation level, infrastructure quality, and urban encroachment. The target variable `FloodProbability` is a continuous value in [0, 1].

This project covers the full ML workflow: exploratory data analysis, feature engineering, model training with early stopping, performance comparison, and submission generation.

## Results

| Model             | MAE      | R²     |
|-------------------|----------|--------|
| Linear Regression | ~0.0200  | ~0.830 |
| LightGBM          | ~0.0185  | ~0.870 |
| XGBoost           | ~0.0187  | ~0.868 |

## Project Structure

```
.
├── notebooks/
│   └── flood_prediction.ipynb   # Main analysis and modeling notebook
├── data/
│   └── flood/
│       ├── train.csv            # Training set (1,117,957 samples)
│       ├── test.csv             # Test set (745,305 samples)
│       ├── sample_submission.csv
│       └── submission.csv       # Generated predictions
├── requirements.txt
├── .gitignore
└── README.md
```

## Setup

```bash
git clone https://github.com/Devaaldo/flood-probability-prediction.git
cd flood-probability-prediction
pip install -r requirements.txt
```

Download the dataset from [Kaggle](https://www.kaggle.com/competitions/playground-series-s4e5/data) and place the CSV files inside `data/flood/`.

Then open and run `notebooks/flood_prediction.ipynb` top to bottom.

## Key Techniques

- Feature engineering: `total_risk` — sum of all 20 risk factors, which correlates strongly with the synthetic target
- LightGBM and XGBoost with early stopping on a held-out validation set (80/20 split)
- No outlier removal — unnecessary for tree-based models on a synthetic dataset
- No feature scaling — not required by gradient boosting methods

## Dataset

Source: Kaggle Playground Series Season 4, Episode 5.  
The dataset is synthetically generated from a real-world flood risk model. All features are integer scores in a common range (~0–18).
