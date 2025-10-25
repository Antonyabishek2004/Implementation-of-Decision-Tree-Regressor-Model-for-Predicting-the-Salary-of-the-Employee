# IMPLEMENTATION-OF-DECISION-TREE-REGRESSOR-MODEL-FOR-PREDICTING-THE-SALARY-OF-THE-EMPLOYEE

## AIM :

To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## EQUIPMENTS REQUIRED :

1. Hardware – PCs

2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM :

1.Import the libraries and read the data frame using pandas.

2.Calculate the null values present in the dataset and apply label encoder.

3.Determine test and training data set and apply decison tree regression in dataset.  

4.Calculate Mean square error,data prediction and r2. 

## PROGRAM :

```

/*

IMPLEMENTATION-OF-DECISION-TREE-REGRESSOR-MODEL-FOR-PREDICTING-THE-SALARY-OF-THE-EMPLOYEE

DEVELOPED BY : ANTONY ABISHEK K 

REGISTER NUMBER : 212223240009

*/

```

```

import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()

data.info

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])

```


## OUTPUT :

## DATA HEAD :

<img width="390" height="265" alt="image" src="https://github.com/user-attachments/assets/4a4db8b8-0cd8-4a6b-9124-012a7ae48294" />

## DATA INFO :

<img width="603" height="237" alt="image" src="https://github.com/user-attachments/assets/108fac4a-cfd0-4e9c-a8ac-8ed5c62250fa" />

## ISNULL() SUM() :

<img width="201" height="88" alt="image" src="https://github.com/user-attachments/assets/cf92bf43-cf14-4931-b5a1-7e874e4d0d68" />

## DATA HEAD FOR SALARY :

<img width="323" height="234" alt="image" src="https://github.com/user-attachments/assets/5eca2dd1-9fb7-42f5-848e-dd2716be9f14" />

## MEAN SQUARED ERROR :

<img width="239" height="38" alt="image" src="https://github.com/user-attachments/assets/d7ab21c0-f51d-4c2c-8d05-ac0a17b84a95" />

## r2 VALUE :

<img width="1065" height="41" alt="image" src="https://github.com/user-attachments/assets/0d49012f-a5bd-41f6-96e5-c5af057b5bb4" />

## DATA PREDICTION :

<img width="311" height="38" alt="image" src="https://github.com/user-attachments/assets/c1a6bcd4-49a0-4ef0-8534-6636ea95f016" />

## RESULT :

Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
