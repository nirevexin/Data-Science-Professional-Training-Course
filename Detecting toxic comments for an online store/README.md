## Project goal: Creating a ML model for determination of comments toxicity.
**Results**:

- We have created a corpus of texts for analysis.
- We cleaned the corpus of signs, stop words, etc., and also lemmatized the corpus texts.
- We converted the corpus texts into vectors for training and prediction.
- We divided the data into training and test samples with a share of 50%.
- We analyzed LinearSVC and logistic regression models; both models had the same accuracy, but we chose the LinearSVC model because of its training speed.
- During testing, the accuracy turned out to be higher than the established minimum (F1 score >= 0.75) so the model is suitable and adequate and therefore recommended.
