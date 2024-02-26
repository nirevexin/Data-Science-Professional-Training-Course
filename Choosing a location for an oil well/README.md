## Project: Choosing a location for an oil well
* **Description**: 
We have been provided with oil samples from three regions in order to build a ML model to determine the region where mining will bring the greatest profit.
* **Goal**: 
Based on exploration data from geologists, selecting from three regions, one in which oil production will bring the greatest profit.
* **Stack**:
`Bootstrap`, `Python`, `NumPy`, `Pandas`, `Scikit-learn`
* **Activity Area**:
`Mining Companies`
* **Technical Area**: 
`Machine Learning`, `Financial analysis`, `Regression`, `Business model development`
* **Data**:
    - Geological exploration data for three regions is in the following files:
        - geo_data_0.csv
        - geo_data_1.csv
        - geo_data_2.csv
    
    - Each contains the following columns:
        - id — unique identifier of the well;
        - f0, f1, f2 - three signs of points (it doesn’t matter what they mean, but the signs themselves are significant);
        - product — volume of reserves in the well (thousand barrels).
    
    ### Results:

- Regression models were trained to predict oil reserves. Prediction accuracy varies across regions;
- The potential profit from the selection of wells based on the model solution was calculated;
- The risks of losses and confidence intervals for each region were calculated;
- Recommendations for choosing regions are given:
    - Region 2 is suitable if the company is not ready for increased risks (1% loss risk), but does not claim the best possible income;
    - Region 3 offers the greatest potential income, but the likelihood of losses is slightly higher (6.4% loss risk).
