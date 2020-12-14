# Mercedes_Kaggle_Challenge

Dataset Link: https://www.kaggle.com/c/mercedes-benz-greener-manufacturing/data

Business Problem: Mercedes-Benz being a pioneer in the European Automobile market ensure vehicle safety and technology features and offers a range of custom options for each car model. Each manufactured vehicle combination must undergo the same rigorous testing to ensure the vehicle is robust enough to keep passenger safe. Depending upon buyer’s requirement, different options and features are offered by Mercedes. This also requires large number of tests for the company’s engineers to conduct. As a consequence, more tests result in more time spent on the test work bench, increasing costs for Mercedes and also generating carbon dioxide emission. Optimizing the speed of their testing system for so many possible feature combinations is complex and time-consuming without a powerful algorithmic approach. In this case study, company challenges us to tackle curse of dimensionality due to so many features provided in the datasets and reduce time that car spends on the test bench.

Problem Statement/Business Objective:
1.	In our data set, ground truth is target variable 'y' representing the time car spend on test bench (in secs). Goal is to reduce time taken by a particular model on test bench which consequently will decrease carbon dioxide emissions associated with the testing procedure.
2.	Predict time in secs (or minutes) not hours with higher R². Here, R² value (Coefficient of determination) is the proportion of the variance in the dependent variable that is predictable from the independent variables.

Observation: It’s a regression challenge because we need predict a continuous target variable (the duration of the test) based on one or more explanatory variables

Datasets observation & Files Descriptions:
1.	Two data sets (train.csv & test.csv) are provided by the Mercedes. Both datasets contains set of variables (features) of Mercedes car. Example: added air suspension, passenger safety belt, 4WD etc.
2.	The train.csv file is the labeled dataset on which different ML models/techniques have to be applied
3.	The test.csv file is the dataset on which predictions are to be made
4.	The target variable y is continuous value which represents the time taken by vehicle for testing in seconds
5.	In test.csv, 'y' variable has to be predicted for 'ID's in this file
6.	There are 377 features out of which 368 are binary, 8 are categorical and 1 is continuous ('y')
7.	The features have names such as ‘X0’, ‘X1’, ‘X2’ and so on
8.	There is a feature ‘ID’ which represents the ID assigned to each vehicle test
9.	Features are anonymous and have no physical representation

Model Selection: There are several basic approaches which are coming in my mind like Baseline Model: Linear Regression, Decision Trees, and Random Forest. I finally decided to move solve this problem by 2 approaches:
1.	Stacking different models (which involves base estimators) and defining a stacked pipeline. In this strategy, some estimators are individually fitted on some training data while a final estimator is trained using the stacked predictions of these base estimators.
2.	By using MLP (Multi-Layer Perceptron) using Keras.

Reason for above two approaches:
1.	Choosing stacking: It works by combining multiple simpler models into one complex model, thereby reducing the variance from a single model and generating better predictions.
2.	Multi-Level Perceptron using Keras: Already familiar with Keras and model architecture

Reflection to my approach:
1.	Load train and test data and Perform EDA for understanding dataset.
2.	Look for different variables present in the data set (categorical, numerical or constant) 2.1) Perform Label Encoding on Categorical data along with normalizing them to bring all values in same range. Label Encoding is preferred over one hot encoding to reduce Computation 2.2) Constant features are removed as its useless because of same values and it won't help the model to learn anything new
3.	We have to perform dimensionality reduction techniques as Mercedes already told us on Kaggle that we have to deal with the curse of dimensionality. Principal Component Analyses (PCA), Independent Component Analyses (ICA) and Truncated Singular Value Decomposition (tsvd). Note: The important features obtained are added to the original features
4.	Preparing final and test set data
5.	Baseline Model: Random Forest Regressor has been created to get an idea of important features which can be thought of using while predicting the model.
6.	Define stacked model and Multi-Layer Perceptron Model
7.	Evaluate the result based on R2 Score
8.	Based on the result, tweak parameters and research more complex models for further improvement

Conclusion:
1.	We have taken the Mercedes-Benz Greener Manufacturing data & applied various ML & DL models on the data.
2.	Stacking model gives best performance on the dataset comparison to MLP using Keras


