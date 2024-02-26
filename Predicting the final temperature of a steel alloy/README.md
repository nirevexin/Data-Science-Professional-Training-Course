## Project: Predicting the final temperature of a steel alloy
### Goal: 
Develop a ML model that will predict the final temperature of a steel alloy.
### Description:
In order to optimize production costs, a metallurgical plant decided to reduce energy consumption at the steel processing stage. To do this, the plant needs to control the temperature of the alloy. The customer wants to use our developed ML model to simulate the technological process.
### Stack: 
`Python`, `Scikit-learn`, `LightGBM`, `NumPy`, `CatBoost`, `Pandas`, `Matplotlib`, `Seaborn`, `Exploratory Data Analysis`
### Activity Area :
`Industry`, `Metallurgy`
### Technical Area:
`Data Analysis`, `Machine Learning`, `Regression`
### Data:
The data consists of several files obtained from different sources:
- data_arc_new.csv — data about electrodes;
- data_bulk_new.csv — data on the supply of bulk materials (volume);
- data_bulk_time_new.csv — data on the supply of bulk materials (time);
- data_gas_new.csv — data on purging the alloy with gas;
- data_temp_new.csv — temperature measurement results;
- data_wire_new.csv — data on wire materials (volume);
- data_wire_time_new.csv - data about wire materials (time).

  
  - File data_arc_new.csv
    - key — batch number;
    - Start of arc heating—heating start time;
    - End of arc heating—time of end of heating;
    - Active power - active power value;
    - Reactive power - the value of reactive power.
  - File data_bulk_new.csv
    - key — batch number;
    - Bulk 1 ... Bulk 15 - volume of supplied material.
  - File data_bulk_time_new.csv
      
    - key — batch number;
    - Bulk 1 ... Bulk 15 - material supply time.
  - File data_gas_new.csv
    - key — batch number;
    - Gas 1 - volume of gas supplied.
  - File data_temp_new.csv
    - key — batch number;
    - Measurement time—measurement time;
    - Temperature—temperature value.
  - File data_wire_new.csv
    - key — batch number;
    - Wire 1 ... Wire 15 - volume of supplied wire materials.
  - File data_wire_time_new.csv
    - key — batch number;
    - Wire 1 ... Wire 15 - time for feeding wire materials.
  
In all files, the key column contains the batch number. There may be several lines in the files with the same key value: they correspond to different iterations of processing.

### Description of the industrial process:
The steel is processed in a metal ladle with a capacity of about 100 tons. To ensure that the ladle can withstand high temperatures, the inside is lined with refractory bricks. Molten steel is poured into a ladle and heated to the desired temperature with graphite electrodes. They are installed in the bucket lid.
Sulfur is removed from the alloy, the chemical composition is adjusted by adding impurities, and samples are taken. The steel is alloyed - its composition is changed - by feeding pieces of the alloy from a bunker for bulk materials or wire through a special tribe apparatus.
Before introducing alloying additives for the first time, the temperature of the steel is measured and its chemical analysis is performed. Then the temperature is raised for several minutes, alloying materials are added and the alloy is purged with an inert gas. Then it is mixed and measurements are taken again. This cycle is repeated until the target chemical composition and optimal melting temperature are achieved.
Then the molten steel is sent for finishing of the metal or enters a continuous casting machine. From there, the finished product comes out in the form of slabs.
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
