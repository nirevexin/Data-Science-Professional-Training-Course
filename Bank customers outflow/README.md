## Project: Bank customers outflow
* **Description**: Customers began to leave the bank in question. Every month. A little, but noticeable. Bank marketers have calculated that it is cheaper to retain current customers than to attract new ones. It is necessary to predict whether the client will leave the bank in the near future or not.
* **Goal**:To train a ML model for identifying clients who may terminate the contract with the bank in order to be able to retain them in a timely manner.
* **Stack**: `Python`, `Pandas`, `Matplotlib`, `Seaborn`, `Scikit-learn` , `NumPy`
* **Activity Area**:
`Business`, `Investments`, `Banking`, `Crediting`
* **Technical Area**: `Machine Learning`, `Classification`
* **Data**:
  - RowNumber - index of the row in the data
  - CustomerId - unique client identifier
  - Surname - surname
  - CreditScore - credit rating
  - Geography - country of residence
  - Gender - gender
  - Age - age
  - Tenure - how many years a person has been a bank client
  - Balance - account balance
  - NumOfProducts — number of bank products used by the client
  - HasCrCard - availability of a credit card
  - IsActiveMember - client activity
  - EstimatedSalary - estimated salary
  - Exited - the fact that the client has left
### Results:
  - We trained several classifier models with a focus on identifying as many customers as possible who will actually churn.
  - The model that gives the most accurate predictions is selected.
  - It was possible to achieve a completeness rate of 61% (f1_score of 0.6132 and an AUC-ROC of 0.8469): this means that practically 2 out of 3 clients selected by the model will actually be at risk.

