# London Bike Share Demand and Maintenance Optimisation
This project uses machine learning to optimise London's bike-sharing system, formally known as Santander Cycles and colloquially known as Boris Bikes. By analysing bike trip data, we predict peak demand times and locations, identify bikes needing maintenance, and assess the performance of different bike models. This helps make the bike-sharing service more reliable and efficient, ensuring bikes are available when and where needed, and minimising downtime due to repairs.

## Non-Technical Explanation of the Project
Imagine you're in charge of a bike-sharing program in London. You want to make sure there are enough bikes at the right places and times, so people don't have to wait. You also want to keep the bikes in good condition so they don't break down. This project uses data on past bike trips to help you figure out where and when to put more bikes, and which bikes might need a tune-up.

## Data
The data used in this project comes from Transport for London (TfL) and includes records of 776,527 bicycle journeys in London during August 2023. The dataset covers trip start and end times, locations, bike models, and durations. The dataset was made available on Kaggle via https://www.kaggle.com/datasets/kalacheva/london-bike-share-usage-dataset/data 

## Model 
We use the XGBoost (Extreme Gradient Boosting) algorithm for prediction. XGBoost is powerful for handling complex relationships between variables and has a track record of success in similar applications.  It is well-suited for predicting bike trip durations and potentially maintenance needs.

## Hyperparameter Optimisation
We optimised several XGBoost hyperparameters using Bayesian Optimisation:

- max_depth (maximum tree depth)
- learning_rate (how fast the model learns)
- n_estimators (number of trees)
- subsample (fraction of data used for each tree)
- colsample_bytree (fraction of features used for each tree)
- By tuning these settings, we aimed to minimise prediction errors and create the most accurate model possible.

## Results
#### Demand Prediction:  
Our model identifies peak demand hours (weekday rush hours and weekends) and high-demand stations, informing where to allocate more bikes.
#### Maintenance Prediction: 
While our model doesn't directly predict maintenance, it lays the foundation for incorporating historical maintenance data to identify bikes that are likely to need repairs.
#### Bike Model Analysis: 
The model also reveals the average trip duration for different bike models, which could help TfL decide which models to purchase in the future.

## Limitations
The model is trained only on August 2023 data, so predictions for other times of year might not be as accurate. 
The dataset may not perfectly represent all bike users, so there might be some bias in the predictions.

