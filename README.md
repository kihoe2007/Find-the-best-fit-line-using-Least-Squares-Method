# Implementation of Univariate Linear Regression
## AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula. 
<img width="231" alt="image" src="https://user-images.githubusercontent.com/93026020/192078527-b3b5ee3e-992f-46c4-865b-3b7ce4ac54ad.png">
4. Compute the y -intercept of the line by using the formula:
<img width="148" alt="image" src="https://user-images.githubusercontent.com/93026020/192078545-79d70b90-7e9d-4b85-9f8b-9d7548a4c5a4.png">
5. Use the slope m and the y -intercept to form the equation of the line.
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:
```
/*
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: kishore S M
RegisterNumber:  212224230131
*/




import numpy as np
import matplotlib.pyplot as plt

x = np.array(eval(input("Enter x values: ")))
y = np.array(eval(input("Enter y values: ")))

x_mean = np.mean(x)
y_mean = np.mean(y)

num = 0
denom = 0
for i in range(len(x)):
    num += (x[i] - x_mean) * (y[i] - y_mean)
    denom += (x[i] - x_mean) ** 2

m = num / denom

b = y_mean - m * x_mean

print("\nSlope (m):", m)
print("Intercept (b):", b)

y_predicted = m * x + b
print("\nPredicted values:", y_predicted)

mse = np.mean((y - y_predicted) ** 2)

rmse = np.sqrt(mse)

print("\nMean Squared Error (MSE):", mse)
print("Root Mean Squared Error (RMSE):", rmse)

plt.scatter(x, y)
plt.plot(x, y_predicted, color='red')
plt.xlabel("X values")
plt.ylabel("Y values")
plt.title("Linear Regression")
plt.show()
```

## Output:
<img width="1325" height="820" alt="image" src="https://github.com/user-attachments/assets/bdafe01a-a4ad-40f7-a102-85ce9494e679" />



## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
