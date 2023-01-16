# Neural_Network_Charity_Analysis

## Overview
The purpose of this analysis was to employ deep learning models to assess the applicants seeking donation. By training a deep learning model on a dataset, the model served as a binary classifier to predict whether applicants would be successful if given funding. 

The deep learning model performed supervised learning by training on the "feature" columns from the dataset to predict a "target" column containing binary values of "0" or "1". Significant preprocessing of data was required to optimize the performance and prepare it for the neural network model. The data was compliled, trained, and the results were evaluated. The details and results of this process are described below.

## Results
### Preprocessing Data for a Neural Network Model
Data from the charity_data.csv was uploaded into a DataFrame and the data was analyzed. Two columns, "EIN" and "NAME", were dropped considering they were unuseful for predicting the success of a donation. 

![image](https://user-images.githubusercontent.com/31812730/212555713-26765d3f-e15a-4fe6-b210-293cbf12c0d5.png)


Column **IS_SUCCESSFUL(Was the money used effectively)**  was considered the target for the model.

Below listed variables are considered the features for the model:

- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested

Number of unique values from each column was calculated as shown below:

![image](https://user-images.githubusercontent.com/31812730/212602879-2f100421-70be-49a0-84c5-57650d11e4ef.png)

All the infrequent categorical values are clolapsed into a single "other" category. The value counts for "APPLICATION_TYPE" were determined as as shown below:

![image](https://user-images.githubusercontent.com/31812730/212603364-cc79b352-8a41-4e53-a22b-d4cbddcdc3d4.png)

The replace method was used to replace all of those values with "other" to reduce the number of unique values in the column.

![image](https://user-images.githubusercontent.com/31812730/212604902-7cce48ae-ed98-44f0-9d63-e7fe72b6c954.png)

The "one hot encoder" was used to create dummy variables and convert all features to numerical format. 

![image](https://user-images.githubusercontent.com/31812730/212607140-e995589a-e982-4cef-a149-6fcbd399a37f.png)

![image](https://user-images.githubusercontent.com/31812730/212607363-f9a6dd80-d6c4-42df-833b-b6431bc883c2.png)

The dataset was separated in the appropriate target(y) and features(X) and split into training and testing sets. The feature data was scaled which altered each variable to have a mean value of zero and a standard deviation of one. 

![image](https://user-images.githubusercontent.com/31812730/212607765-7b417d8e-dd5d-4451-803e-aa3f5294c321.png)

### Compile, Train, and Evaluate the Model
Continue using the AlphabetSoupCharity.ipynb file where you’ve already performed the preprocessing steps from Deliverable 1.
Create a neural network model by assigning the number of input features and nodes for each layer using Tensorflow Keras.
Create the first hidden layer and choose an appropriate activation function.
If necessary, add a second hidden layer with an appropriate activation function.
Create an output layer with an appropriate activation function.
Check the structure of the model.
Compile and train the model.
Create a callback that saves the model's weights every 5 epochs.
Evaluate the model using the test data to determine the loss and accuracy.
Save and export your results to an HDF5 file, and name it AlphabetSoupCharity.h5.

### Optimize the Model

## Summary
