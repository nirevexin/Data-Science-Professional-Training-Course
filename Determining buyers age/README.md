## Project: Determining buyers age
### Description:
A chain supermarket is implementing a computer vision system to process customer photos. Photo recording in the checkout area will help determine the age of customers in order to analyze purchases and offer products that may be of interest to buyers of this age group and monitor the integrity of cashiers when selling alcohol.
### Goal:
Conducting a study to create a neural network that will help determine the age of a person from photographs.
### Stack: `Python`, `Keras`
### Activity Area:
`Offline`, `Business`
### Technical Area:
`Computer Vision (CV)`, `Machine Learning`, `Neural Network`
### Results:
- A Neural Network model was created and trained, for which it is possible to obtain a metric value of at least MAE = 6.68 in the test sample, which is lower than the value required by the condition: 8.
- The Bread-Salt supermarket chain can use the resulting model as a computer system for processing customer photos.
- It is possible to improve the MAE by adding more epochs and trying different values for the Adam optimizer.
