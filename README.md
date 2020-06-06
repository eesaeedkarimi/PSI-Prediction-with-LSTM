# YapAiTek-Assessment
Predict Pollutant Standards Index (PSI) levels in Singapore with precision.  

In this assessment, we seek to understand changes in air quality in Singapore from 2016 to 2019.  
The data is about the Pollutant Standards Index (PSI), specifically PM2.5.  
There are four bands on the PM2.5 concentration scale:  
* 0 to 55 for Normal  
* 56 to 150 for Elevated  
* 151 to 250 for High  
* Very high for any higher readings. 

It is asked you to predict PSI levels in Singapore with precision.  

PSI records are in [psi_df_2016_2019.csv](https://github.com/eesaeedkarimi/YapAiTek-Assessment/blob/master/psi_df_2016_2019.csv)

[PSI_Prediction.ipynb](https://github.com/eesaeedkarimi/YapAiTek-Assessment/blob/master/PSI_Prediction.ipynb) presents a solotion to this task.

The solution consists of 5 steps.

0. Setup  
Imports and defining base functions
1. Read, Explore and Prepare Data  
Reading Data  
Preparing date and time  
Adding a column for **diff_hour**: difference of record time between consecutive rows  
Data exploration  
Plotting Histogram of PSI values and diff_hour value  
Sampling the dataset  
2. Creating Train and Test Datasets
3. Training the Model  
Scaling data with MinMax Scaler  
Splitting Validation Set for checking **Early Stopping** condition to prevent overfitting.  
Making training sequence  
Defining and Initializing the Model  
Training Model for 150 epochs and checking Early Stopping condition  
Saving the trained Model  
Training and Validation Loss  
4. Prediction  
Making Predictions on the Test set  
Error of Predictions  
Plottting the results  
Making Prediction on one sample

## Future work  
There some suggestions to make a better project and better predictions.
1. Model training can be done with another code so that the result does not change every time we run this file.
2. Predictions on test set can be done using predicted values.
3. Input feature can be all of the features of dataset, not just the 'national' PSI.
4. This data is cyclostationary and statistical properties vary cyclically with time. Probably these statistical properties has a period of one week or one year. Therefore, we can add 2 new parameters that indicate the time of the week (0 to 6 days or 0 to 7\*8-1) and the time of the year (0 to 354 days or 0 to 365\*8-1) to acheive better predictions.
