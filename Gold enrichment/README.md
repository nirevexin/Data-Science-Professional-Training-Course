### Goal: create a ML model to predict the gold recovery rate from a gold ore
### Process description and Data
Description of each stage:
- 1 **Flotation**
     
A mixture of gold ore is fed into the flotation unit. After enrichment, a rough concentrate and “waste tailings” are obtained, that is, the remains of a product with a low concentration of valuable metals.
The stability of this process is affected by the inconsistent and suboptimal physicochemical state of the flotation pulp (a mixture of solid particles and liquid).

- 2 **Cleaning**
     
The rough concentrate undergoes two purifications. The output is a final concentrate and new tailings.

#### Data Description
##### Technological process
- Rougher feed - feedstock
- Rougher additions (or reagent additions) - flotation reagents: Xanthate, Sulphate, Depressant
  - Xanthate - xanthate (promoter, or flotation activator);
  - Sulphate - sulfate (in this production, sodium sulfide);
  - Depressant - depressant (sodium silicate).
- Rougher process - flotation
- Rougher tails - waste tailings
- Float banks - flotation unit
- Cleaner process - cleaning
- Rougher Au - rough gold concentrate
- Final Au - final gold concentrate
#### Stage parameters
- air amount - air volume
- fluid levels - fluid level
- feed size - size of raw material granules
- feed rate - feed speed
### Results:
During the implementation of this project the following was carried out:

- A SweetViz report was created.
- The missing values were filled, duplicates and data types were checked and propered.
- The correct calculation of enrichment efficiency was verified.
- Missing columns were installed into data_test.
- Analysis of changes in the metal concentration (Au, Ag, Pb) between cleaning phases (in the raw material, in the rough concentrate, in the concentrate after the first cleaning and in the final concentrate) was done:
  - The concentration of gold increases at each stage.
  - After flotation, the concentration of all metals increases.
  - After the first stage of purification, the concentration of silver decreases, and the concentration of lead continues to increase.
  - After the second stage of purification, we can see that the concentration of silver continued to decrease, but the concentration of lead remained the same.
- The size of the feedstock granules at the flotation stage between the training sample and the testing sample was statistically compared:
  - low probability to be different, so the model assessment should be normal.
- The outliers where the metal concentration is zero were removed.
- Analysis of the total concentration of metals at different stages was done:
  - The total concentration increases significantly after flotation.
  - After the first cleaning, it decreases sharply, and after the second cleaning, it increases again.
  - In the end, the combined concentration of metals remains slightly higher than that which was after the second cleaning but less than that which was after flotation, and the distribution shifts towards the average.
- A function to calculate sMAPE was created.
- The correlation among the features in both rougher and final phases was checked and the correlated features were removed to avoid interference in the prediction quality.
- Feature dimensionality was reduced via UMAP for better predicting performance.
- Considering the nature of the data, several predicting models were created (Ridge Reg., Random Forest Reg., Decision Tree Reg. and LGBM) and the two best models for each, flotation and final stage, were selected:

    - Flotation stage:
      -  1. `Ridge(alpha=0.8) with sMAPE = 8.30`
      -  2. `DecisionTreeRegressor(max_depth=1) with sMAPE = 8.39`
    - Final stage:
      -  1. `DecisionTreeRegressor(max_depth=1) with sMAPE = 10.54`
      -  2. `RandomForestRegressor(max_depth=2, n_estimators=10) with sMAPE = 10.62`
- All of the seleceted best models were tested on the test sample and the DecisionTreeRegressor(max_depth=1) turned out to be the adequate for both stages, although with a sMAPE just minimally better than the random model's.

Summary:

The models that turned out to be the best are just slightly better than a random model; this might be due to the data nature itself:
- our `best model's sMAPE 9.03` vs. `9.16 of a random model's sMAPE` on `flotation stage`
- our `best model's sMAPE 9.73` vs. `9.94 of a random model's sMAPE` on the `final stage`
- `our concluding sMAPE 9.55` vs. `9.75 of a random model's concluding sMAPE`

Although there turned out to be an adequate model for each phase in the testing, this cannot guarantee that they will be adequate once implemented in production, since, for instance, during the training phase, the best model for the flotation phase later gave worse results than the random model on the testing sample. It really depends on the data in question to be predicted, and given the nature of the data, it is unlikely that better results can be obtained.
