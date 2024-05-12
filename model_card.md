# Model Card for London Bike Share Demand and Maintenance Prediction

## Model Description

**Input:** 

- Categorical: Start station, End station, and day of the week (one-hot encoded).
- Numerical: Hour of the day (cyclically encoded as sine and cosine components).

**Output:** 

- The model predicts the duration of a bike trip in minutes.

**Model Architecture:** 

The model is based on XGBoost (Extreme Gradient Boosting), a decision-tree-based ensemble machine learning algorithm. XGBoost is known for its strong predictive power and ability to handle various types of data. The specific hyperparameters used in the final model were determined through Bayesian Optimization.

## Performance

The model's performance was evaluated using Root Mean Squared Logarithmic Error (RMSLE) on a held-out test set. This metric is chosen because it is less sensitive to outliers and penalizes under-prediction more than over-prediction, aligning with the goals of optimising bike availability. The final RMSLE achieved on the test set was 0.7000535564455026.

## Limitations

This model is limited by its reliance on data from August 2023 only, potentially leading to less accurate predictions for other months or seasons. Additionally, potential biases in the dataset may affect predictions for specific groups or situations. Currently, the model does not predict bike maintenance needs due to a lack of relevant data. 

## Trade-offs

The model balances complexity and interpretability, opting for the powerful but less transparent XGBoost algorithm to prioritise prediction accuracy. This approach also involves a trade-off between prediction accuracy and computational cost due to the use of Bayesian Optimisation for hyperparameter tuning.
