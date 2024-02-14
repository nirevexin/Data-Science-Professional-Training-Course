## Project goal: Development of a system for predicting taxi order volume.
### Results:
- Trends and seasonality were analyzed and several models were created to predict future orders in hourly intervals. 
- All models have very similar accuracy and outperform predictions without a model by at least 65 percent.
- However, the LGBMRegressor(random_state = 12345, max_depth = 7, num_leaves = 91) model was chosen as the best model because its accuracy is slightly better.
- In the end, we compared the values of targets and forecasts, and the model turns out to be quite accurate, excluding some rare unpredictable peaks in orders.
