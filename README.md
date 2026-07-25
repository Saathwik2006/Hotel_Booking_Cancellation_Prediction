# Hotel Booking Cancellation Prediction

## Overview
This project aims to predict whether a hotel booking will be cancelled using machine learning. The dataset contains booking information such as lead time, guest details, room type, meal plan, booking channel, and previous booking history.

## Current Progress
- Loaded and explored the dataset
- Performed data cleaning
- Handled missing values
- Identified categorical and numerical features
- Performed initial exploratory data analysis

## Tech Stack
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost

## Feature Engineering

Extended the dataset by creating several domain-specific features to better represent customer booking behavior and improve predictive performance.

### Engineered Features
- Total Guests
- Total Nights
- Previous Cancellation Rate
- Total Previous Bookings
- ADR per Guest
- ADR per Night
- Lead Time per Night
- Lead Time × Previous Cancellation Rate
- Guests per Night
- Parking per Guest
- Room Change Indicator
- Meal Indicator
- Seasonal Booking
- Booking-related categorical bins (Lead Time, ADR, Guests, Nights, Waiting List, Special Requests, etc.)

The impact of each engineered feature was evaluated through multiple experiments before finalizing the feature set.

## Model Development

Implemented multiple machine learning algorithms and compared their predictive performance on the hotel booking cancellation dataset.

### Models Implemented
- Logistic Regression
- Random Forest Classifier
- Xgboost Classifier
- Xgboost Classifier ( tuned )







### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix
- Stratified Cross Validation

The models were trained on both the original and engineered feature sets to analyze the impact of feature engineering on prediction performance.

### Evaluation

| Model                  | Accuracy | Precision | Recall | F1 Score | ROC-AUC | Mean CV Accuracy |
|-----------------------:|---------:|----------:|-------:|---------:|--------:|-----------------:|
| Logistic Regression    |  0.8301  |  0.8313   | 0.7447 |  0.7856  |  0.9128 |      0.8229      |
| Random Forest          |  0.8710  |  0.8800   | 0.8045 |  0.8400  |  0.9128 |      0.8694      |
| Xgboost                |  0.8935  |  0.9020   | 0.8359 |  0.8677  |  0.9596 |      0.8869      |
| Xgboost ( Feature Eng )|  0.8912  |  0.8822   | 0.8538 |  0.8678  |  0.9606 |      0.8907      |
| XGBoost ( Tuned Model )|  0.8968  |  0.8724   | 0.8454 |  0.8587  |  0.9630 |      0.8959      |

### Model Comparison Summary

- **Logistic Regression:** Simple baseline model with **83.01%** accuracy.
- **Random Forest:** Improved predictive performance with **87.10%** accuracy.
- **XGBoost (Baseline):** Achieved the highest baseline accuracy of **89.35%**.
- **XGBoost (Feature Engineering):** Improved recall and cross-validation performance through engineered features.
- **XGBoost (Final Optimized Model):** Produced the best overall performance with **89.68% Accuracy**, **96.30% ROC-AUC**, and **89.59% Mean Cross-Validation Accuracy** after hyperparameter tuning and feature selection.
- The small difference between the test Accuracy (**89.68%**) and Mean Cross-Validation Accuracy (**89.59%**) demonstrates that the model generalizes well to unseen data and is not significantly overfitted.


## Dataset Expansion Comparison

To evaluate the impact of increasing the dataset size, the final optimized XGBoost model was trained on both the original dataset (79,330 bookings) and the expanded dataset (1,18,987 bookings).

| Dataset Size | Test Accuracy | Mean CV Accuracy |
|--------------|--------------:|-----------------:|
| ~79,330 Bookings | **89.17%** | **89.11%** |
| 1,18,987 Bookings| **89.68%** | **89.59%** |

### Observations

- Expanding the dataset by nearly **50%** improved both the test accuracy and cross-validation accuracy.
- Test Accuracy increased from **89.17%** to **89.68%**.
- Mean Cross-Validation Accuracy increased from **89.11%** to **89.59%**.
- The close agreement between test accuracy and cross-validation accuracy in both experiments indicates **strong generalization with minimal overfitting**.
- Increasing the amount of training data improved the model's robustness and stability while maintaining consistent predictive performance on unseen data.
