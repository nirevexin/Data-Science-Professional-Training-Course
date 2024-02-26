## Project goal: Develop a ML model that will predict the final temperature of a steel alloy.
### Description: In order to optimize production costs, the "Steel Bird" metallurgical plant decided to reduce energy consumption at the steel processing stage. To do this, the plant needs to control the temperature of the alloy. The customer wants to use our developed ML model to simulate the technological process.
### Goal: Develop a ML model that will predict the final temperature of a steel alloy.
### Stack:: `Python`, `Scikit-learn`, `LightGBM`, `NumPy , `CatBoost`, `Pandas`, `Matplotlib`, `Seaborn`, `Exploratory Data Analysis`
### Activity Area : `Industry`, `Metallurgy`
### Technical Area: `Data Analysis`, `Machine Learning Regression`
### Results:
- Data on temperature, gas volume, sand material volume, wire material volume, active and reactive power were analyzed, filtered and cleaned.
- The data was collected into a common dataframe, analyzed and cleaned.
- In order to correctly merge the dataframes, two new features were created: arc_heating_duration_sum and active_power_mean.
- The data was scaled and divided into training and test sets in a 75/25 ratio.
- Ridge, Lasso, Random Forest, LightGBM and CatBoost models were tested using the best hyper-parameters tuned during the process.
- Ridge(alpha=0.8) was selected as the best model, with a MAE of 6.44 on the training set and the fastest training time.
- The best model was successfully tested on the test set, showing a MAE of 6.40, outperforming the random model (MAE of 8.36).
- A conclusion was drawn about the importance of each feature.
### Recommendations:
- It is advisable to take into account that for the selected predictive model, in each batch, the initial temperature and the total duration of arc heating play an important role.
