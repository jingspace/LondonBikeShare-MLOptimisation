# Model Card for London Bike Share Demand and Maintenance Prediction

## Model Description

## Objective
The model is designed to:
- Identify high-demand areas and peak times to optimise the allocation of bikes, ensuring availability when and where needed.
- Predict maintenance needs based on detailed usage patterns, aiming to minimise downtime and enhance service reliability.
- Analyse the durability and operational performance of different bike models within urban conditions to inform future fleet compositions and purchasing decisions.

**Input:** 

- Categorical: Start station, End station, and day of the week (one-hot encoded).
- Numerical: Hour of the day (cyclically encoded as sine and cosine components).

**Output:** 

- The model predicts the duration of a bike trip in minutes.

**Model Architecture:** 

The model is based on XGBoost (Extreme Gradient Boosting), a decision-tree-based ensemble machine learning algorithm. XGBoost is known for its strong predictive power and ability to handle various types of data. The specific hyperparameters used in the final model were determined through Bayesian Optimisation.

## Performance

The model’s performance is primarily evaluated using the Mean Squared Error (MSE), which helps in quantifying the accuracy of predictions regarding trip durations and maintenance scheduling. Additionally, feature importance analysis is conducted to pinpoint the most influential factors affecting bike trip durations.

#### The model training process incorporates several steps:
- Feature Engineering: This includes the extraction of time-related features and the encoding of categorical geographic data to enhance the model's predictive accuracy.
- Data Splitting: The dataset is meticulously split into training, validation, and testing sets to ensure that the model is robust and performs well on unseen data.

## Limitations

This model is limited by its reliance on data from August 2023 only, potentially leading to less accurate predictions for other months or seasons. Additionally, potential biases in the dataset may affect predictions for specific groups or situations. Currently, the model does not predict bike maintenance needs due to a lack of relevant data. 

## Trade-offs

The model balances complexity and interpretability, opting for the powerful but less transparent XGBoost algorithm to prioritise prediction accuracy. This approach also involves a trade-off between prediction accuracy and computational cost due to the use of Bayesian Optimisation for hyperparameter tuning.

While the model provides valuable insights, it is recommended that continuous data monitoring and model retraining sessions are conducted to adapt to changing usage patterns and infrastructure developments. Further tuning and integration of real-time data could significantly improve the model's predictive capabilities.

## Updates and Versioning
- Last Updated: May 12, 2024
- Recent updates include refining the model training process and improving the accuracy of performance metrics.
