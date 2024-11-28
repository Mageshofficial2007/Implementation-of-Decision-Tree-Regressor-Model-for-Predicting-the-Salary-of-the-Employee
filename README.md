# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Importing Libraries and Reading Data
2. Exploring the Data
3. Encoding Categorical Data
4. Selecting Features and Target Variables
5. Splitting Data into Training and Testing Sets
6. Training the Decision Tree Regressor Model
7. Making Predictions
8. Evaluating the Model: R² Score
9. Predicting for a New Example


## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: MAGESH BOOPATHI.M
RegisterNumber: 24900855 
```
```python
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder ()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2, random_state = 2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
print(mse)
r2 = metrics.r2_score(y_test,y_pred)
print(r2)
dt.predict([[5,6]])
```

## Output:
![Screenshot 2024-11-28 173839](https://github.com/user-attachments/assets/01d197dc-2ca4-463b-a7e8-2a4d8b4ff157)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
