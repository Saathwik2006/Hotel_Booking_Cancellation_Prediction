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

| Model               | Accuracy | Precision | Recall | F1 Score | ROC-AUC | Mean CV Accuracy |
|--------------------:|---------:|----------:|-------:|---------:|--------:|-----------------:|
| Logistic Regression |  0.8301  |  0.8313   | 0.7447 |  0.7856  |  0.9128 |      0.8229      |
| Random Forest       |  0.8710  |  0.8800   | 0.8045 |  0.8400  |  0.9128 |      0.8694      |
 
