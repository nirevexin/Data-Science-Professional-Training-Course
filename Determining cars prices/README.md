## Project goal: Development of a system for recommending a price for a car based on its description.

### Results:

- We analyzed the data and made the necessary adjustments.
- We split the data into training and testing samples, digitized the categorical data, and scaled it for optimal model performance.
- We found the optimal parameters for the Ridge Regression, RandomForestRegressor and LightGBM models and chose the model that performed best, with a RMSE of 1623, namely LightGBM.
- We tryied the chosen model on the testing sample and the result was a RMSE of 1584, meaning a satisfactory outcome.
- Using LightGBM, we found out which features most influence the forecasts:
  - From most to least:
 - 1 registration year
 - 2 power
- 3 mileage
- Next, we tested the model only with these features and the results were as follows:
    - An RMSE of 2036 (worsened by 28.53%), but still below 2500, which is what is required.
    - Training and prediction speeds improved by 66% (2.3s vs 0.78s) and 75.75% (0.33s vs 0.08s), respectively.
### Recommendation
- Based on this information, the most recommended model is LGBMRegressor(learning_rate = 0.3, max_depth = 9, num_leaves = 91), taking into account only the features of vehicle registration year, vehicle power and mileage. However, if it's necessary to gain even more precision in exchange for faster calculation, then, the LGBMRegressor(learning_rate = 0.3, max_depth = 9, num_leaves = 91) model can be used with all the features (except for those specifically removed during the work on the project).
