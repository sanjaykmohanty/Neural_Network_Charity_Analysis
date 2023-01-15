# Neural_Network_Charity_Analysis

## Overview
The purpose of this analysis was to employ deep learning models to assess the applicants seeking donation. By training a deep learning model on a dataset, the model served as a binary classifier to predict whether applicants would be successful if given funding. 

The deep learning model performed supervised learning by training on the "feature" columns from the dataset to predict a "target" column containing binary values of "0" or "1". Significant preprocessing of data was required to optimize the performance and prepare it for the neural network model. The data was compliled, trained, and the results were evaluated. The details and results of this process are described below.

## Results
### Preprocessing Data for a Neural Network Model
To begin with, data from the charity_data.csv was uploaded into a DataFrame and the data was analyzed. Two columns, "EIN" and "NAME", were dropped as they were found to be unuseful for predicting the success of a donation. 

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

Determine the number of unique values for each column.
For those columns that have more than 10 unique values, determine the number of data points for each unique value.
Create a density plot to determine the distribution of the column values.
Use the density plot to create a cutoff point to bin "rare" categorical variables together in a new column, Other, and then check if the binning was successful.
Generate a list of categorical variables.
Encode categorical variables using one-hot encoding, and place the variables in a new DataFrame.
Merge the one-hot encoding DataFrame with the original DataFrame, and drop the originals. At this point, your merged DataFrame should look like this:


Split the preprocessed data into features and target arrays.
Split the preprocessed data into training and testing datasets.
Standardize numerical variables using Scikit-Learn’s StandardScaler class, then scale the data.

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
