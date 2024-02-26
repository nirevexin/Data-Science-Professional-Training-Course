## Project: Telephone rate recommendation
* **Description**: A mobile operator has found out that many customers use archived tariffs. They want to build a system that can analyze customer behavior and offer users one of the new tariffs.
* **Goal**: Offering clients the most appropriate rate for them.
* **Stack**: `Python`,  `Pandas`, `Matplotlib`, `Seaborn`, `Scikit-learn`
* **Activity Area** : Telecoms
* **Technical Area**: `Machine Learning`, `Classification`

* **Metrics requirements**:
* - Accuracy > 0'75
*  **Data**:
    - calls — number of calls,
    - minutes — total duration of calls in minutes,
    - messages — number of SMS messages,
    - mb_used — consumed Internet traffic in MB,
    - is_ultra — what tariff the client uses during the month (“Ultra” - 1, “Smart” - 0).
    
### Results:

- We have visually examined the distribution of both  Smart` and `Ultra` rates in terms of minutes, calls, messages and MB consumed.
- We checked the correlation between the parameters:
- Calls and minutes correlated, so we removed the calls column in order to improve our model's results.
- We explored the `Tree Classifier`, `Random Forest Classifer` and the `Logistic Regression` models, found the best hyperparameters for each and selected the best of them, which turned out to be RandomForestClassifier(max_depth=10, n_estimators=60, random_state=12345) with an `accuracy of 0.8`.
- We checked the models for adequacy using the DummyClassifier model; all of them turned out to be adequate.
- `RandomForestClassifier(max_depth=10, n_estimators=60, random_state=12345)` is the endorsed model for recommending a rate to a client.
