# Neural_Network_Charity_Analysis

## Overview
The purpose of this analysis was to employ deep learning models to assess the applicants seeking donation. By training a deep learning model on a dataset, the model served as a binary classifier to predict whether applicant would be successful if given funding. 

The deep learning model performed supervised learning by training on the "feature" columns from the dataset to predict a "target" column containing binary values of "0" or "1". Significant preprocessing of data was required to optimize the performance and prepare it for the neural network model. The data was compiled, trained, and the results were evaluated. The details and results of this process are described below.

## Results
### Preprocessing Data for a Neural Network Model
Data from the charity_data.csv was uploaded into a DataFrame and the data was analyzed. Two columns, “EIN” and “NAME” were dropped considering they were useful for predicting the success of a donation. 

![image](https://user-images.githubusercontent.com/31812730/212555713-26765d3f-e15a-4fe6-b210-293cbf12c0d5.png)


Column **IS_SUCCESSFUL (Was the money used effectively)**  was considered the target for the model.

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

All the infrequent categorical values are collapsed into a single "other" category. The value counts for "APPLICATION_TYPE" were determined as shown below:

![image](https://user-images.githubusercontent.com/31812730/212603364-cc79b352-8a41-4e53-a22b-d4cbddcdc3d4.png)

The replace method was used to replace all those values with "other" to reduce the number of unique values in the column.

![image](https://user-images.githubusercontent.com/31812730/212604902-7cce48ae-ed98-44f0-9d63-e7fe72b6c954.png)

The "one hot encoder" was used to create dummy variables and convert all features to numerical format. 

![image](https://user-images.githubusercontent.com/31812730/212607140-e995589a-e982-4cef-a149-6fcbd399a37f.png)

![image](https://user-images.githubusercontent.com/31812730/212607363-f9a6dd80-d6c4-42df-833b-b6431bc883c2.png)

The dataset was separated in the appropriate target(y) and features(X) and split into training and testing sets. The feature data was scaled which altered each variable to have a mean value of zero and a standard deviation of one. 

![image](https://user-images.githubusercontent.com/31812730/212607765-7b417d8e-dd5d-4451-803e-aa3f5294c321.png)

### Compile, Train, and Evaluate the Model
The initial model design included 80 neurons for the first hidden layer and 30 neurons for the second hidden layer. Both layers employed the "relu" activation function and the final output layer utilized the "sigmoid" function to classify the result as a 0 or 1 which was unsuccessful vs successful prediction.

![image](https://user-images.githubusercontent.com/31812730/212609314-39e687ea-c8ad-4126-87c7-105764248b46.png)

An evaluation was employed on the neural network design which resulted in a loss of about 74% and an accuracy score of about 55%. 

![image](https://user-images.githubusercontent.com/31812730/212609816-e402f1f7-d266-483a-a76d-4369e86fd590.png)

### Optimize the Model
Additional adjustments were made to the model to improve the performance of the model, an attempt to achieve above 75% accuracy. 

The results of the adjustments are shown below:

**Attempt # 1**
The first attempt was to check if dropping extra features would improve performance. Two features "USE_CASE_Other", "AFFILIATION_Other" were dropped. 

![image](https://user-images.githubusercontent.com/31812730/212611722-68c5b586-e23f-4e77-b52b-651fb6e521c3.png)

This model design also included 80 neurons for the first hidden layer and 30 neurons for the second hidden layer. Both layers employed the "relu" activation function and the final output layer utilized the "sigmoid" function. 

An evaluation was employed on the neural network design which resulted in a loss of about 58% and an accuracy score of about 73%. 

![image](https://user-images.githubusercontent.com/31812730/212611601-41c7572f-af57-4df8-a303-bdd94b29a9f8.png)

**Attempt # 2**
The second attempt was to check if adding an additional hidden layer would improve performance. This model design also included 80 neurons for the first hidden layer, 30 neurons for the second hidden layer, and 15 neurons for the third hidden layer. All three layers employed the "relu" activation function and the final output layer utilized the "sigmoid" function. 

An evaluation was employed on the neural network design which resulted in a loss of about 59% and an accuracy score of about 73%. 

![image](https://user-images.githubusercontent.com/31812730/212612528-21a516b7-4620-4c4b-a90a-60e8c9f87ab0.png)

**Attempt # 3**
The third attempt was to check if using a different activation function would improve performance. This model design included 80 neurons for the first hidden layer, 30 neurons for the second hidden layer, and 15 neurons for the third hidden layer. All three layers employed the "tanh" activation function, and the final output layer utilized the "sigmoid" function. 

An evaluation was employed on the neural network design which resulted in a loss of about 56% and an accuracy score of about 73%. 

![image](https://user-images.githubusercontent.com/31812730/212613039-2f990572-4264-4a63-9a00-52e0f2349200.png)

## Summary
Deep neural network machine learning model produced an useful binary classifier in predicting whether funding an applicant would produce successful results. After dropping two features "USE_CASE_Other", "AFFILIATION_Other" the model performance improved substantially. However, after adjusting the model three times, the predictive capability never reached above 75% accuracy. 

Additional optimization techniques such as dropping more features or employing a different activation function needed to achieve the required above 75% accuracy.

Neural networks are not the only machine learning method available. There are several alternatives exist, these alternatives may provide better performances.

Here are some of the alternatives:
- **Random forests** consist of an ensemble of decision trees, each trained with a random subset of the training dataset. This method corrects a decision tree’s tendency to overfit the input data
- **Support vector machines** attempt to map the input data into a space where it is linearly separable into different categories
- **k-nearest neighbors algorithm (KNN)** looks for the values in the training dataset that are closest to a new input, and combines the target variables associated with those nearest neighbors into a new prediction
- **Symbolic regression** technique tries to find explicit mathematical formulas that connect the input variables to the target variable
