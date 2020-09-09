# Credit_Card_Fraud_Detection
## 1.Introduction

## 2.Dataset


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
#### Data preprocessing

##### 1.1 Null Value</br>
```
My findings:</br>
    1.There are 30 predictor variables and 1 target variable with 284807 rows.</br>
    2.there is no null values in this data set.</br>
    3.Columns Time and Amount are not scaled.</br>
    4.The data set is highly unbalanced. There are 99.82% of transaction are non-fraud and 0.17% are fraud.</br>
    5.The distribution of Amount is extremely skewed to the right, centered at about 88. There are some values apparently present on the higher end.</br>
```
##### 1.2Feature Scaling</br>
```
Time and Amount are not scaled, so I apply stadardization to both columns.
```
##### 1.3 Feature Selection
```
There are 30 predictor variabels in this data. We could extract informative variables and reduce the computational cost of modeling.
It seems that v17,v14,v12,v10,v16,v3,v7,v11 are informative variables.
```
#### Model Selection & Performance
