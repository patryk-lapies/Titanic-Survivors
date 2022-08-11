
# Titanic Survivors


The goal of this project is to predict survivors from the Titanic shipwreck 
based on this data: [Titanic data](https://www.kaggle.com/competitions/titanic/data?select=train.csv) .
Its purpose is to learn and practice the usage of the Logistic Regression algorithm.
## Technologies

- Python 3.9.12
- Scikit-Learn 1.0.2
- Numpy 1.22.3
- Pandas 1.4.2
- Seaborn 0.11.2
## About the Data

This dataset contains data about 891 Titanic passengers including 11 features, and a target variable defining whether they survived or not. 
## Data Cleaning
- Dropped PassengerId, Name, Ticket and Cabin columns
- Filled missing values in Age column with mean
- Removed outliers from numeric columns
- Filled missing values in Embarked column with most occurring value
- Transformed categorical columns using get_dummies

### Standarisation
Used Standard Scaler and for some cases MinMaxScaler from sklearn to standardised all numeric data and test which one is better for this problem.
## Models created
### Evaluation 
Each created model was evaluated using an accuracy score, precision score, and ROC AUC score. But mainly focused on improving accuracy.
### Basic model
The first Logistic Regression model was based on all numeric features and it scored 73.5% accuracy, 74% precision and 0.78 ROC AUC score.

### Next Models
Next models were built using a created function that searches for the best combination of features for the model.

#### Model A
This model used only Pclass, Age, Parch columns and it helped to score 75.7% accuracy, 76% precision score and 0.76 ROC AUC score.
#### Model B
This model used data from only Age, SibSp, Fare columns with removed outliers and it helped to score 77.6% accuracy, 83% precision score and 0.77 ROC AUC score.
#### Model C
This model used data from only Pclass, Age, SibSp, Fare columns with standardised data using Standard scaler and it scored 77.6% accuracy, 78% precision score and 0.77 ROC AUC score.
#### Model D
This model used data from only Pclass, Age, Parch, Fare columns with standardised data using MinMax scaler and it scored 76.6% accuracy, 74% precision score, and 0.79 ROC AUC score.
#### Model E
This model used all transformed categorical and numerical columns with standardised data using Standard scaler and it scored 83% accuracy, 82% precision score, and 0.80 ROC AUC score.
#### Model F
This model used only transformed Sex_male column and Age column with standardised data using Standard scaler and it scored 83% accuracy, 82% precision score, and 0.80 ROC AUC score.
## Conlusion
|    Model    | accuracy | precision | ROC AUC |
|:-----------:|:--------:|:---------:|:-------:|
| Basic model |   73.5%  |    74%    |   0.78  |
|   Model A   |   75.7%  |    76%    |   0.76  |
|   Model B   |   77.6%  |    83%    |   0.77  |
|   Model C   |   77.6%  |    78%    |   0.77  |
|   Model D   |   76.6%  |    74%    |   0.79  |
|   Model E   |    83%   |    82%    |   0.8   |
|   Model F   |    83%   |    82%    |   0.8   |

Model F is the best with 83% accuracy because it only uses 2 features to predict the target value.