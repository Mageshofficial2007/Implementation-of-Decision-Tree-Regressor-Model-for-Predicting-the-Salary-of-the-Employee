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
INFO:

![Screenshot 2024-11-29 091631](https://github.com/user-attachments/assets/7aeaca0e-be19-4feb-92e7-b584dbd983e0)

HEAD:

![Screenshot 2024-11-29 091647](https://github.com/user-attachments/assets/5a55c1f5-2445-4ede-a97f-b9c8c51beeb6)

POSITION:

![Screenshot 2024-11-29 091656](https://github.com/user-attachments/assets/bf49af4d-61be-4cbd-a78b-c9f097e0aaef)

SALARY:

![Screenshot 2024-11-29 091704](https://github.com/user-attachments/assets/1e5b9f53-12cb-42cc-b188-a03e0529d80f)


SELECTION:

![Screenshot 2024-11-29 091712](https://github.com/user-attachments/assets/96d79d4a-f64b-41c8-9d33-d0ec8cdd138b)

MSE:

![Screenshot 2024-11-29 091718](https://github.com/user-attachments/assets/dbc2d4aa-1a53-4b17-88a6-63a329feddb7)

PREDICTION:

![Screenshot 2024-11-29 091725](https://github.com/user-attachments/assets/56433ace-7b4d-4c80-99c4-b1fda4491d0f)


![Screenshot 2024-11-29 091747](https://github.com/user-attachments/assets/c549da97-2034-49f8-9f5b-e0dd7e120a6f)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
