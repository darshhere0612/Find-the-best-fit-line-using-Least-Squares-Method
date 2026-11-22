Implementation of Univariate Linear Regression
Name: Darshan J
Reg No:21222402008
AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook
Algorithm
Get the independent variable X and dependent variable Y.
Calculate the mean of the X -values and the mean of the Y -values.
Find the slope m of the line of best fit using the formula.
image

4. Compute the y -intercept of the line by using the formula:
image

5. Use the slope m and the y -intercept to form the equation of the line. 6. Obtain the straight line equation Y=mX+b and plot the scatterplot.
Program:

import numpy as np
import matplotlib.pyplot as plt

#GETTING INPUT
x = np.array(eval(input()))#EXAMPLE INPUT - 2,9,5,5,3,7,1,8,6,2
y = np.array(eval(input()))#EXAMPLE INPUT - 69,98,82,77,71,84,55,94,84,64

#FINDING MEAN 
x_mean = np.mean(x)
y_mean = np.mean(y)

#CALCULATING NUMERATOR AND DENOMINATOR
num = 0
denom = 0
for i in range(len(x)):
    num += (x[i] - x_mean) * (y[i] - y_mean)
    denom += (x[i] - x_mean) ** 2
m = num / denom

b = y_mean - m * x_mean
print(m, b)

#FINDING Y-PREDICTED
y_predicted = m * x + b
print(y_predicted)

#PLOTTING GRAPH
plt.scatter(x, y)
plt.plot(x, y_predicted, color='red')
plt.show()
Output:
image image
Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
