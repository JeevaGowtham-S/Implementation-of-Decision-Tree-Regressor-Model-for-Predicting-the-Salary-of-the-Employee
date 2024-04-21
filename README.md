# Ex 07-Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:

To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:

1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the libraries and read the data frame using pandas.

2.Calculate the null values present in the dataset and apply label encoder.

3.Determine test and training data set and apply decison tree regression in dataset.

4.calculate Mean square error,data prediction and r2.

## Program:

```py
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: JEEVAGOWTHAM S
RegisterNumber: 212222230053
```

```py

import pandas as pd
data=pd.read_csv("Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
x.head()

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

## Output:

## data.head()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/1cdae00b-0abc-4e46-aa06-6244666fef39)


## data.info
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/cb6cae99-b292-4b08-a019-e7c6389a6598)


## isnull() and sum()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/070e3d6f-ebdb-4651-a61e-e998457ee854)


## data.head() for salary
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/ede2b717-82ef-4455-87f5-b64546d95adf)

## MSE value
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/cda22bdb-4809-4ca7-ab49-50e0e5c69b1a)


## r2 value
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/c06d9423-b31c-4107-a12f-8129cf062508)


## data prediction
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118042624/e6b58b32-72a9-451d-86b8-d5e3f6fdc5f0)


## Result:

Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
