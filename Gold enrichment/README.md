
## Results:
During the implementation of this project the following was carried out:

- A SweetViz report was created.
- The missing values were filled, duplicates and data types were checked
- The correct calculation of enrichment efficiency was verified.
- Missing columns were installed into data_test.
- Analysis of changes in the metal concentration between cleaning phases was done:
        - The concentration of gold increases at each stage.
        - After flotation, the concentration of all metals increases.
        - After the first stage of purification, the concentration of silver decreases, and the concentration of lead continues to increase.
        - After the second stage of purification, we can see that the concentration of silver continued to decrease, but the concentration of lead remained the same.
- The size of the feedstock granules at the flotation stage between the training sample and the testing sample was statistically compared: low probability to be different, so the model assessment should be normal.
- A function to calculate sMAPE was created.
- Feature dimensionality was reduced via UMAP for better predicting performance.
- Considering the nature of the data, several predicting models were created (Ridge Reg., Random Forest Reg., Decision Tree Reg. and LGBM) and the two best models for each, flotation and final stage, were selected:

    - Flotation stage:
            1. `Ridge(alpha=0.8) with sMAPE = 8.30`
            2. `DecisionTreeRegressor(max_depth=1) with sMAPE = 8.39`
    - Final stage:
            1. `DecisionTreeRegressor(max_depth=1) with sMAPE = 10.54`
            2. `RandomForestRegressor(max_depth=2, n_estimators=10) with sMAPE = 10.62`
- All of the seleceted best models were tested on the test sample and the DecisionTreeRegressor(max_depth=1) turned out to be the adequate for both stages, although with a sMAPE just minimally better than the random model's.

Summary:

The models that turned out to be the best are just slightly better than a random model; this might be due to the data nature itself:
- our `best model's sMAPE 9.03` vs. `9.16 of a random model's sMAPE` on `flotation stage`
- our `best model's sMAPE 9.73` vs. `9.94 of a random model's sMAPE` on the `final stage`
- `our concluding sMAPE 9.55` vs. `9.75 of a random model's concluding sMAPE`

Although there turned out to be an adequate model for each phase in the testing, this cannot guarantee that they will be adequate once implemented in production, since, for instance, during the training phase, the best model for the flotation phase later gave worse results than the random model on the testing sample. It really depends on the data in question to be predicted, and given the nature of the data, it is unlikely that better results can be obtained.
