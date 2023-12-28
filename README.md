# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of equations n.
Initialize matrix matrix and solution vector x.

2. Use nested loops to input coefficients into the augmented matrix.

3. For each pivot row, eliminate coefficients below the diagonal by subtracting a multiple of the pivot row.

4. Starting from the last row, solve for variables backward using the updated matrix.

5. Print the solution vector x with a formatted message for each variable.
## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Thrinesh Royal
RegisterNumber: 212223230226
*/
import numpy as np
import sys
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    if matrix[i][j]==0.0:
        sys.exit("Divide by zero error")
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#Back Substitution
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
```
## Output:

![Screenshot 2023-12-28 210557](https://github.com/Thrineshroyal/Gaussian/assets/145741928/3c453ec0-0e7e-4374-bdd1-91d06dbf9062)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

