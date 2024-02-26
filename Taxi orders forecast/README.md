## Project: Taxi orders forecast
* **Description**: A taxi company collected historical data on taxi bookings at airports. To attract more drivers during peak periods, they need to predict the number of taxi orders for every next hour. 
* **Goal**: Development of a system for predicting order volume.
* **Tools**: `Statsmodels`, `Augmented Dickey-Fuller test`, `Python`, `Scikit-learn`, `LightGBM`, `NumPy`, `Pandas`, `Matplotlib`, `Seaborn`
* **Activity Area** : Business, Internet Services, Start-ups
* **Technical Area**: `Time Series`, `Machine Learning` `Regression`
* **Data**:
  - The number of orders is in the `num_orders` column. The other column belongs to the order date. 
  
### Results:
- Trends and seasonality were analyzed and several models were created to predict future orders in hourly intervals. 
- All models have very similar accuracy and outperform predictions without a model by at least 65 percent.
- However, the LGBMRegressor(random_state = 12345, max_depth = 7, num_leaves = 91) model was chosen as the best model because its accuracy is slightly better.
- In the end, we compared the values of targets and forecasts, and the model turns out to be quite accurate, excluding some rare unpredictable peaks in orders.
