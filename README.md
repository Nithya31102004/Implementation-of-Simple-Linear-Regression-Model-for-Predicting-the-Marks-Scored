
# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries and read the dataframe.
2. Assign hours to X and scores to Y.
3. Implement training set and test set of the dataframe
4. Plot the required graph both for test data and training data.
## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by:Nithya.T
RegisterNumber:2305001023
*/
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
df=pd.read_csv('/content/student_scores.csv')
#displaying the content in datafile
df.head()
df.tail()
x=df.iloc[:,:-1].values
print(x)
y=df.iloc[:,1].values
y
#splitting train and test data
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(x_train,y_train)
y_pred=regressor.predict(x_test)
#displaying predicted values
y_pred
#displaying actual values
y_test
#graph plot for training data
plt.scatter(x_train,y_train,color="blue")
plt.plot(x_train,regressor.predict(x_train),color="red")
plt.title("Hours vs Scores (Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_squared_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print("MAE = ",mae)
rmse=np.sqrt(mse)
print("RMSE = ",rmse)
```
## Output:
![image]![Screenshot 2024-03-19 232008](https://github.com/Nithya31102004/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/164048368/4c10f602-907f-4b64-9245-8e8ae00adeb3)




## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
