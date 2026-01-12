
🚕 NYC Taxi Fare Prediction using Machine Learning

1. Project Overview

This project focuses on predicting taxi fares using historical NYC taxi trip data. The goal is to build an end-to-end machine learning pipeline involving exploratory data analysis, feature engineering, model training, hyperparameter tuning, and explainability using SHAP.

The solution emphasizes data-driven decision making, model robustness, and interpretability, following real-world data science best practices.

2. Dataset

Train data: 500,000 rows (synthetically generated, NYC-bounded)

Test data: 100,000 rows

Target variable: fare_amount

Time range: January 2009 – June 2015 (UTC)

3. Exploratory Data Analysis (EDA)

Key EDA steps included:

Target variable distribution and outlier detection

Passenger count validation

Geospatial sanity checks for latitude and longitude

Trip distance analysis using Haversine formula

Temporal analysis (hourly, daily, monthly patterns)

Train–test distribution consistency checks

4. Feature Engineering

Engineered features based on domain knowledge:

Geospatial features

Haversine distance

Manhattan distance

Directional deltas (latitude & longitude)

Temporal features

Hour of day, day of week, month, year

Rush-hour, night-time, weekend flags

Statistical transformations

Log-transformed distance to handle skewness

All features were applied consistently across train and test datasets to avoid leakage.

5. Modeling Approach

Models trained and evaluated:

Linear Regression (baseline)

Random Forest Regressor

Gradient Boosting Regressor

XGBoost Regressor (final model)

XGBoost was selected for its:

Strong performance on tabular data

Built-in regularization

Fast training and scalability

Robust generalization

6. Hyperparameter Tuning

Used RandomizedSearchCV

Tuned depth, learning rate, subsampling, and regularization parameters

Optimized using RMSE as the evaluation metric

7. Model Explainability (SHAP)

Applied SHAP TreeExplainer

Identified distance-based features as dominant predictors

Temporal features (rush hour, night trips) showed positive impact on fare

Enabled both global and local interpretability

8. Evaluation Metric

Root Mean Squared Error (RMSE) on validation set

9. Key Takeaways

Trip distance is the strongest predictor of fare

Temporal features significantly improve prediction accuracy

Regularized boosting models generalize better than unregularized ensembles

SHAP enhances trust and transparency in ML predictions

10. Future Improvements

Add traffic/weather data

Perform spatial clustering

Deploy model as an API

Experiment with LightGBM