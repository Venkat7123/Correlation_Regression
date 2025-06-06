# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```
import matplotlib.pyplot as plt
import numpy as np
import math

# Input data
x = [int(i) for i in input("Enter x values (space-separated): ").split()]
y = [int(i) for i in input("Enter y values (space-separated): ").split()]
N = len(x)

# Initialize sums
Sx = Sy = Sxy = Sx2 = Sy2 = 0

# Compute required sums
for i in range(N):
    Sx += x[i]
    Sy += y[i]
    Sxy += x[i] * y[i]
    Sx2 += x[i] ** 2
    Sy2 += y[i] ** 2

# Correlation coefficient
r = (N * Sxy - Sx * Sy) / (math.sqrt(N * Sx2 - Sx ** 2) * math.sqrt(N * Sy2 - Sy ** 2))
print("The Correlation coefficient is %0.3f" % r)

# Regression line Y on X
byx = (N * Sxy - Sx * Sy) / (N * Sx2 - Sx ** 2)
xmean = Sx / N
ymean = Sy / N
print("The Regression line Y on X is::: y = %0.3f + %0.3f (x - %0.3f)" % (ymean, byx, xmean))

# Plotting
plt.scatter(x, y, label='Data points')

def Reg(x_val):
    return ymean + byx * (x_val - xmean)

x_vals = np.linspace(min(x), max(x), 100)
y_vals = Reg(x_vals)

plt.plot(x_vals, y_vals, 'r', label='Regression Line')
plt.xlabel('x-data')
plt.ylabel('y-data')
plt.legend()
plt.title('Regression Line Y on X')
plt.grid(True)
plt.show()


```
# Output 
![image](https://github.com/user-attachments/assets/7229d8b2-caf5-43d5-b25b-6c8a761a7c66)


# Result
The Correlation and regression for data analysis of objects from feeder using probability distribution are calculated. 
