## Project: Detecting toxic comments for Wikishop online store
* **Description**:
An online store launches a new service. Now users can edit and add product descriptions, just like in wiki communities. That is, customers suggest their edits and comment on the changes of others. We need a tool that will look for toxic comments and send them for moderation.
* **Goal**:
Creating a ML model for determination of comments toxicity.
* **Stack**:
`Pandas`, `Python`, `nltk`, `tf-idf`, `Word2vec`, `tqdm`, `Scikit-learn`
* **Activity Area**:
`Internet Services`, `Start-Ups`
* **Technical Area**:
`NLP`, `Machine Learning`, `Classification`
* **Data**:
  - The `text` column in it contains the comment text, and `toxic` is the target attribute.
### Results:

- We have created a corpus of texts for analysis.
- We cleaned the corpus of signs, stop words, etc., and also lemmatized the corpus texts.
- We converted the corpus texts into vectors for training and prediction.
- We divided the data into training and test samples with a share of 50%.
- We analyzed LinearSVC and logistic regression models; both models had the same accuracy, but we chose the LinearSVC model because of its training speed.
- During testing, the accuracy turned out to be higher than the established minimum (F1 score >= 0.75) so the model is suitable and adequate and therefore recommended.
