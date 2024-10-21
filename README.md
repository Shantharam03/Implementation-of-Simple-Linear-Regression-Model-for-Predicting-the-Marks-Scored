# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard libraries.
2.Set variables for assigning dataset values.
3.Import linear regression from sklearn.
4.Assign the points for representing in the graph.
5.Predict the regression for marks by using the representation of the graph.
6.Compare the graphs and hence we obtained the linear regression for the given datas.


## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: shantharam M
RegisterNumber:  24900113
*/
```
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

from sklearn.metrics import mean_absolute_error,mean_squared_error

df = pd.read_csv('student_scores.csv')

print(df)

df.head(0)

df.tail(0)

print(df.head())

print(df.tail())

x = df.iloc[:,:-1].values

print(x)

y = df.iloc[:,1].values

print(y)

from sklearn.model_selection import train_test_split

x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 1/3,random_state = 0)

from sklearn.linear_model import LinearRegression

regressor = LinearRegression()

regressor.fit(x_train,y_train)

y_pred = regressor.predict(x_test)

print(y_pred)

print(y_test)

mae = mean_absolute_error(y_test,y_pred)

print("MAE: ",mae)

mse = mean_squared_error(y_test,y_pred)

print("MSE: ",mse)

rmse = np.sqrt(mse)

print("RMSE: ",rmse)

# graph plotting for trainig set data

plt.scatter(x_train,y_train)

plt.plot(x_train,regressor.predict(x_train) , color ='blue')

plt.title("Hours vs Scores(training set)")

plt.xlabel("Hours")

plt.ylabel("Scores")

plt.show()

# graph plotting for test set data

plt.scatter(x_test,y_test)

plt.plot(x_test,regressor.predict(x_test),color = 'black')

plt.title("Hours vs Scores(testing set)")

plt.xlabel("Hours")

plt.ylabel("Scores")

plt.show()



## Output:
![Screenshot 2024-10-18 094055](https://github.com/user-attachments/assets/aab52013-f354-44b5-97f6-506987bedf82)
![Scree![Screenshot 2024-10-18 094158](https://github.com/user-attachments/assets/e72b4da0-b05f-4e04-88c8-26d2d15f23aa)
nshot 20![Screenshot 2024-10-18 094211](https://github.com/user-attachments/assets/64500aff-2fd5-4b36-b52b-3a9dae96d3c6)
24-10-18 094131](https://github.com/user-attachments/assets/14f9fab2-d63d-460c-9bb7-1769383303c3)



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
