<h2>The folder contains the following files:</h2>

1. README.md
2. eda.ipynb
3. models.ipynb
4. requirements.txt

<h2>Instructions for Executing the Pipeline and Modifying Parameters:</h2>

1. Install the required Python libraries listed in requirements.txt
2. Open and run the eda.ipynb Jupyter Notebook for data exploration and preprocessing
3. Open and run the models.ipynb Jupyter Notebook for model training, evaluation, and deployment

<h2>Description of Logical Steps/Flow of the Pipeline:</h2>

1. Data Cleaning: Remove rows with missing/abnormal values, standardise data units/formats, and handle data type conversion.
2. Data Exploration: Analyse the dataset structure, generate summary statistics, and examine categorical variables using countplots.
3. Visualisation: Create visuals to identify variables with potential relationships with the target variable 'no_show'.
4. Hypothesis Testing: Use Chi-Square test to determine significant relationships between variables and 'no_show'.
5. Model Selection: Choose suitable machine learning models (e.g., Logistic Regression, Decision Tree, Random Forest) based on the target variable and predictors.
6. Model Training: Train the selected models using 80% of the dataset.
7. Model Evaluation: Evaluate model performance using accuracy, precision, recall, F1 score, and confusion matrix metrics.

<h2>Overview of Key Findings from EDA:</h2>

A histogram was used to show the distribution of prices for Show and No Show. For other variables, a countplot was used to compare the proportion of No Show to Show. A higher variation of No Show to Show across the different features in the variable would thus indicate a relationship with 'no_show'. From the observation, we find that 'branch', 'country', 'first_time', and 'room' have a significant relationship with 'no_show'. Therefore, these parameters will be used to train the Machine Learning Models.

<h2>Features Processing:</h2>

| Features                             | How is it Processed                                                                                |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------|
| num_adults| Convert the 'num_adults' variable from string to numeric data type|
| price| Convert all prices in the 'price' column from SGD and USD to SGD only, and convert to float|
| checkout_day| Remove rows where the 'checkout_day' variable has negative values|
| arrival_month| Convert all the months in 'arrival_month' to lowercase and capitalise the first letter|
|branch, country, first_time, room| Map categorical variables 'branch', 'country', 'first_time', and 'room' to numerical labels for machine learning modelling|

<h2>Choice of Models for Machine Learning Tasks:</h2>

<h3>Model 1: Binary Logistic Regression</h3>

Logistic Regression is suitable as it takes in two or more predictor variables to predict the outcome of the categorical target variable 'no_show'. In this case, the predictor variables are all categorical.

<h3>Model 2: Multi-Variate Decision Tree</h3>

A Decision Tree is suitable as it provides a clear and interpretable structure that shows how decisions are made based on the predictor variables. This can help us understand the factors influencing the target variable and determine the predictors that have a greater impact on the target variable. Another advantage of a Decision tree is that it can capture non-linear relationships between predictors and the target variable.

<h3>Model 3: Random Forest Classification</h3>

Random Forest can capture non-linear relationships between predictor variables and the target variable 'no_show'. It is an ensemble learning method that combines multiple decision trees, each trained on a random subset of the data and variables. This ensemble approach helps reduce overfitting and improves generalisation performance compared to a single decision tree.

<h2>Evaluation of Models:</h2>

All the 3 Machine Learning Models are evaluated using the Confusion Matrix, which uses the Test dataset to test the outcome of the model (i.e. to determine the number of entries that were predicted correctly and wrongly using the model). The accuracy of the model is measured by taking (True Positive + True Negative) / Total number of entries. The accuracy refers to the probability of the model in predicting the outcome correctly. In summary, the Logistic Regression, Decision Tree, and Random Forest yield an accuracy of 0.71, 0.70, and 0.72, respectively.
