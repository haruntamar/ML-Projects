# EA FC 24 Player Value Predictor

Machine learning model to predict player values in EA Sports FC 24 using Random Forest Regression.

## Overview

This project uses player statistics from EA FC 24 to predict player market values. The model analyzes various player attributes such as pace, shooting, passing, defending, dribbling, and physicality to estimate their market value in euros.

## Dataset

- **Source**: FIFA player dataset (male_players.csv)
- **Version**: FIFA 24 players only
- **Target Variable**: Player value in EUR
- **Features Used**:
  - Age
  - Pace
  - Shooting
  - Passing
  - Defending
  - Dribbling
  - Physicality

## Model Details

- **Algorithm**: Random Forest Regressor
- **Number of Estimators**: 100
- **Train/Test Split**: 80/20
- **Random State**: 23 (for data split), 42 (for model)

## Performance Metrics

- **Test Score (R²)**: 0.9665
- **Train Score (R²)**: 0.9950
- **Mean Absolute Error (MAE)**: €0.97

The model shows excellent performance with high R² scores on both training and test sets, indicating strong predictive capability.

## Data Preprocessing

1. Filter dataset for FIFA 24 players only
2. Select relevant features
3. Remove goalkeepers (by dropping rows with null pace, shooting, or dribbling)
4. Clean missing values
5. Drop non-predictive features (short_name, wage_eur, overall, potential)

## Requirements

```
numpy
pandas
scikit-learn
```

## Usage

1. Ensure you have the `male_players.csv` dataset
2. Run the Jupyter notebook `eafc24valuePredictor.ipynb`
3. The model will train and display performance metrics

## Notes

- Goalkeepers are excluded from the analysis as they have different attribute patterns
- The model uses only basic player statistics, excluding overall rating and potential to avoid data leakage
- Wage information is also excluded to ensure the model learns from skill attributes rather than salary indicators
