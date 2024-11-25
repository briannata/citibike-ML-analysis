# Citi Bike Machine Learning Analysis

Analyzing NYC Citi Bike data with machine learning to uncover trends in rider demographics, peak times, bike types, and station usage. Uses regression, forecasting, clustering, and neural network techniques to provide insights for enhancing bike-sharing infrastructure and user experience.

## Baseline Models

We used linear regression to predict trip duration based on start station, end station, latitude, longitude, month, day, hour, minute, member type, and bike type. We also used logistic regression to classify whether a user was a casual user or Citi Bike member based on those variables. These baseline models helped us find a base performance so we can compare it to our other models.

## Random Forest Regression

We used a Random Forest Regressor to predict trip duration based on features such as starting and ending locations, trip start time, day of the week, and whether the trip occurred on a weekend. The model was fine-tuned using RandomizedSearchCV for hyperparameter optimization.

Root Mean Squared Error (RMSE): 4.67 minutes
On average, the model's predictions deviate from actual trip durations by 4.67 minutes.

Baseline Comparison:

The baseline model (predicting the mean trip duration) had an RMSE of 7.32 minutes. The Random Forest model reduced prediction error by approximately 36%, indicating strong performance.

R² Score: 0.59
The model explains 59% of the variance in trip durations, capturing meaningful patterns but leaving room for further improvement.

## Clustering

We used a K-Means Clustering algorithm to find clusters of Citi Bike stations in New York City. We found that 5 clusters was too many with strong overlapping behavior. We found that 3 clusters was more distinct and were in Midtown, East Village, and Murray Hill.

## Forecasting

We used the ARIMA and SARIMA algorithms to perform time-series forecasting and predict the number of daily Citi Bike rides. We found that the SARIMA algorithm had a better performance as it can account for seasonality whereas the ARIMA model works best on stationary data. 

## Neural Network

We used a neural network to perform regression and predict trip duration. We ended up with a model that performed quite well and decreased the average loss over the 10 epochs. The model had a MAE 6.4901 on the test set, meaning that that the predicted trip durations deviate from the actual trip durations by about 6.4901 minutes.