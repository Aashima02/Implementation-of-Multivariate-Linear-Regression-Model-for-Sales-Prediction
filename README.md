# Implementation-of-Multivariate-Linear-Regression-Model-for-Sales-Prediction

## AIM:
To write a program to implement the multivariate linear regression model for sales prediction.

## EQUIPMENTS REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## ALGORITHM:
1. Import the required standard libraries.
2. Upload the dataset
3. Declare X and Y variable with respect to the dataset.
4. Predict the values.
5. Find the required line that fits the data using Mean Square Error(MSE).
6. Print the Mean Square Error(MSE) and R square error.
7. End the program.

## PROGRAM:
```

Program to implement the multivariate linear regression model for sales prediction.
Developed by: Aashima Nazreen Sayeed S
RegisterNumber: 212221240002

import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Advertising.csv")
df.head()
df.describe()
df.isnull().sum()
df.shape
X = df[["TV", "Radio", "Newspaper"]]
X
Y = df["Sales"]
Y
from sklearn.model_selection import train_test_split
X_train,X_test,Y_train,Y_test = train_test_split(X,Y,test_size = 0.2,random_state = 101)
from sklearn.linear_model import LinearRegression
l = LinearRegression()
l.fit(X_train,Y_train)
Y_pred = l.predict(X_test)
X_test
print("Regression slope: ",l.coef_[0])
print("Regression Intercept: ",l.intercept_)
Y_pred
from sklearn import metrics
MSE = metrics.mean_squared_error(Y_test,Y_pred)
print("MSE is {}".format(MSE))
r2 = metrics.r2_score(Y_test,Y_pred)
print("R squared error is {}".format(r2))
l.predict([[150.3,240.5,234.5]])

```

## OUTPUT:
![output](./output.png)


## RESULT:
Thus the program to implement the multivariate linear regression model for sales prediction is written and verified using python programming.
