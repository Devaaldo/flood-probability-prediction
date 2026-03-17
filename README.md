# Flood Risk Prediction Model

A machine learning solution for predicting flood probability based on environmental and geographical factors. This project implements multiple regression models and compares their performance on a large-scale dataset.

## Overview

The project analyzes 20+ environmental features to predict flood probability, including monsoon intensity, deforestation, infrastructure quality, and climate change indicators. The dataset contains over 1.1 million training samples from the Kaggle Playground Series competition.

## Models

Three regression models are implemented and evaluated:

- Linear Regression: R² = 0.828
- Gradient Boosting Regressor: R² = 0.619
- LARS: R² = 0.001

Linear Regression achieves the best performance with MAE of 0.329.

## Dataset

Features include environmental and geographical factors:
- Monsoon Intensity, Topography, River Management
- Deforestation, Urbanization, Climate Change
- Infrastructure and population metrics
- Historical disaster preparedness data

Dataset source: [Kaggle Playground Series S4E5](https://www.kaggle.com/competitions/playground-series-s4e5/)

## Project Structure

```
flood_prediction.ipynb          # Model training and evaluation
data/flood/
├── train.csv                   # Training dataset (1,117,957 samples)
├── test.csv                    # Test dataset (745,305 samples)
└── sample_submission.csv       # Submission format
```

## Requirements

- Python 3.11+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Usage

1. Place dataset files in `data/flood/` directory
2. Open and run `flood_prediction.ipynb` in Jupyter or VS Code
3. The notebook performs EDA, feature engineering, and model training
4. Generated predictions can be formatted for competition submission

## Data Processing

- Outlier detection using IQR method
- Feature standardization using StandardScaler
- No missing values detected in the dataset
- 845,886 samples retained after outlier removal
