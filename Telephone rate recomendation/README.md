## Project goal: Develop a classification system to offer clients the most appropriate phone rate for them.
### Results:

- We have visually examined the distribution of both "Smart" and "Ultra" rates in terms of minutes, calls, messages and MB consumed.
- We checked the correlation between the parameters:
- Calls and minutes correlated, so we removed the calls column in order to improve our model's results.
- We explored the Tree Classifier, Random Forest Classifer and the Logistic Regression models, found the best hyperparameters for each and selected the best of them, which turned out to be RandomForestClassifier(max_depth=10, n_estimators=60, random_state=12345) with an accuracy of 0.8.
- We checked the models for adequacy using the DummyClassifier model; all of them turned out to be adequate.
- RandomForestClassifier(max_depth=10, n_estimators=60, random_state=12345) is the endorsed model for recommending a rate to a client.
