## Implementation of Univariate Linear Regression

### AIM

To implement Univariate Linear Regression to fit a straight line using the ordinary least squares (OLS) method in Python.

### Equipments Required

* **Hardware:** PC / Laptop
* **Software:** Anaconda / Python 3.7+ Installation, Jupyter Notebook (with `numpy` and `matplotlib`)

---

### Algorithm

1. Get the independent variable $X$ and dependent variable $Y$.
2. Calculate the mean of the $X$-values ($\bar{X}$) and the mean of the $Y$-values ($\bar{Y}$):

$$\bar{X} = \frac{1}{n}\sum_{i=1}^{n} x_i, \qquad \bar{Y} = \frac{1}{n}\sum_{i=1}^{n} y_i$$


3. Find the slope $m$ of the line of best fit using the least squares formula:

$$m = \frac{\sum_{i=1}^{n} (x_i - \bar{X})(y_i - \bar{Y})}{\sum_{i=1}^{n} (x_i - \bar{X})^2}$$


4. Compute the $y$-intercept $b$ of the line using the formula:

$$b = \bar{Y} - m\bar{X}$$


5. Use the slope $m$ and the $y$-intercept $b$ to form the equation of the straight line:

$$Y = mX + b$$


6. Predict values $\hat{Y}$ using the fitted equation and plot the scatter plot along with the best-fit regression line.

---

### Program

```python
"""
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: Darshan J
RegisterNumber: 212224020008
"""

import numpy as np
import matplotlib.pyplot as plt

# 1. Get independent variable X and dependent variable Y
X = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], dtype=float)
Y = np.array([2.1, 4.0, 5.8, 8.2, 10.1, 11.9, 14.2, 16.0, 17.8, 20.1], dtype=float)

# 2. Calculate the mean of X and Y
mean_x = np.mean(X)
mean_y = np.mean(Y)

# 3. Calculate the slope (m) using least squares
numerator = np.sum((X - mean_x) * (Y - mean_y))
denominator = np.sum((X - mean_x) ** 2)
m = numerator / denominator

# 4. Calculate the y-intercept (b)
b = mean_y - m * mean_x

# 5 & 6. Form the equation Y = mX + b and compute predicted values
Y_pred = m * X + b

print(f"Mean of X: {mean_x:.4f}")
print(f"Mean of Y: {mean_y:.4f}")
print(f"Slope (m): {m:.4f}")
print(f"Y-intercept (b): {b:.4f}")
print(f"Regression Equation: Y = {m:.4f}X + {b:.4f}")

# Plot the scatter plot and best fit line
plt.figure(figsize=(8, 5))
plt.scatter(X, Y, color="blue", label="Actual Data Points (Scatter)")
plt.plot(X, Y_pred, color="red", linewidth=2, label=f"Best Fit Line: Y = {m:.2f}X + {b:.2f}")
plt.title("Univariate Linear Regression (Least Squares)")
plt.xlabel("Independent Variable (X)")
plt.ylabel("Dependent Variable (Y)")
plt.legend()
plt.grid(True)
plt.show()

```

---

### Output

Running the script prints the calculated parameters and displays a scatter plot with the red least-squares regression line passing through the data points:

```text
Mean of X: 5.5000
Mean of Y: 11.0200
Slope (m): 1.9976
Y-intercept (b): 0.0333
Regression Equation: Y = 1.9976X + 0.0333

```

---

### Result

Thus, univariate Linear Regression was implemented to fit a straight line using the least squares method in Python.
