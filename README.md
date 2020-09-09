# Credit_Card_Fraud_Detection
## 1.Introduction

Machine learning models allow us to deal with classification problems. Take this dataset as an example, machine learning helps us to determine whether the transaction is legit or fraudulent. Since most of the transactions are not fraudulent, dealing with imbalanced data would be the main challenge during the process of this analysis. Therefore, our main goal in this analysis is to build a model that can correctly indentify the type of a transaction, even the dataset is unbalanecd.

## 2.Dataset
This is one of the most classic imbalance datasets on Kaggle. The datasets contains two-days transations made by credit cards. The names of the features are not shown due to the confidential issues.

## 3.Overview of Analysis
```
1.Data Preprocessing
  1.1 Null Values
  1.2 Feature Scaling
  1.3 Feature Selection
2.Model Selection & Performance
  2.1 Before oversampling or undersampling
  2.2 Oversampling
  2.2 Undersampling
  2.3 SMOTE
```
### Data preprocessing

##### 1.1 Null Value&EDA
![distribution of Amount](https://user-images.githubusercontent.com/32606310/92606682-ca149300-f2e5-11ea-9af5-c617e810622f.png)
![unbalanced](https://user-images.githubusercontent.com/32606310/92606635-bec16780-f2e5-11ea-8a65-21ad52276e62.png)

```
My findings:
    1.There are 30 predictor variables and 1 target variable with 284807 rows.
    2.There is no null values in this data set.
    3.Columns Time and Amount are not scaled.
    4.The data set is highly unbalanced. There are 492 frauds out of 284808 transactions, where frauds accounting for 0.17%.
    5.The distribution of Amount is extremely skewed to the right, centered at about 88. There are some values apparently present on the higher end.
```
##### 1.2 Feature Scaling
```
Time and Amount are not scaled, so I apply stadardization to both columns.
```
##### 1.3 Feature Selection

```
There are 30 predictor variabels in this data. 
To reduce the computational cost of modeling, feature selection helps us to extract more informative variables. Since the input variables are numerical and output variables are categorical, ANOVA correlation coefficient is used to select the TOP 10 variables.After applying feature selection methods, it seems that v17,v14,v12,v10,v16,v3,v7,v11 are informative variables.
```
![Score](https://user-images.githubusercontent.com/32606310/92606616-b9641d00-f2e5-11ea-98e3-0c52504efe1b.png)

### Model Selection & Performance
##### 2.0 Imbalanced datasets
```
In this analysis, I use decision tree to build the model, where gini is the criteria that measure the quality of a split.
The accuracy of the model is 0.99, which is extremely high. However, Accuracy is not meaningful when we measure the performance of imbalanced datasets. Other indicators such as Recall, F1-score and ROC sould be checked as well.</br>
```
![tree](https://user-images.githubusercontent.com/32606310/92608011-6b501900-f2e7-11ea-957f-419d1432869a.PNG)</br>
![confusion matrix_imbalanced](https://user-images.githubusercontent.com/32606310/92607985-668b6500-f2e7-11ea-906c-d299321defbe.PNG)</br>
![ROC_imbalanced](https://user-images.githubusercontent.com/32606310/92607531-d5b48980-f2e6-11ea-8940-432e8f733c14.png)</br>

##### 2.1 Oversampling
```
Oversampling is to make the number of positive cases equal to that of negative cases, so replicate the positive cases.
```
![confusion matrix_over](https://user-images.githubusercontent.com/32606310/92607987-6723fb80-f2e7-11ea-99ec-d6c7a089fcf0.PNG)</br>
![ROC_over](https://user-images.githubusercontent.com/32606310/92607535-d5b48980-f2e6-11ea-8043-65fc26f35dfd.png)</br>
##### 2.2 Undersampling
```
randomly deleted some negative cases to make the number of positive cases equal that of negative cases.
```
![confusion matrix_under](https://user-images.githubusercontent.com/32606310/92608001-6a1eec00-f2e7-11ea-9532-3b23ca318f15.PNG)</br>
![ROC_under](https://user-images.githubusercontent.com/32606310/92607545-d816e380-f2e6-11ea-8d30-0eaa6c4caaa5.png)</br>
##### 2.3 SMOTE
```
Based on the distribution features of positive cases, reproduce some similar positve instances.
```
![confusion matrix_SMOTE](https://user-images.githubusercontent.com/32606310/92607995-68edbf00-f2e7-11ea-8982-52dce3f060e1.PNG)</br>
![ROC_smote](https://user-images.githubusercontent.com/32606310/92607537-d6e5b680-f2e6-11ea-882d-fa177447f1cc.png)</br>
### Conclution
After oversampling or undersampling, our model have higher accuracy and AUC, compared to the imbalanced one.
