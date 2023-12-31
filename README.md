# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import necessary libraries (numpy, sys).
2. Get the number of equations (n) from the user.
3. Create an augmented matrix (a) of size n x (n+1) filled with zeros.
4. Create a solution vector (x) of size n filled with zeros.
5. Input coefficients of the equations into the augmented matrix.
6. Iterate through each row (i) from 0 to n-1:
7. Check for division by zero: If a[i][i] is 0, exit with an error message.
8. Iterate through each row below the current row (j) from i+1 to n-1:
9. Calculate the elimination ratio: ratio = a[j][i] / a[i][i].
10. Subtract the current row multiplied by the ratio from the row below: a[j][k] = a[j][k] - ratio * a[i][k] for all columns k.
11. Calculate the last unknown variable: x[n-1] = a[n-1][n] / a[n-1][n-1].
12. Iterate through the remaining rows (i) in reverse order from n-2 to 0:
Set x[i] to the last element of the current row: x[i] = a[i][n].
13. Subtract the product of elements in the current row and corresponding solution values from x[i]: x[i] = x[i] - a[i][j] * x[j] for j from i+1 to n-1.
14. Divide x[i] by the diagonal element: x[i] = x[i] / a[i][i].
15. Print the solutions in the format "X%d = %0.2f" for each variable.

## Program:
```
'''#Program to solve a matrix using Gaussian elimination without partial pivoting.
#Developed by: VENKATANATHAN P R
#RegisterNumber: 23000285
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
    
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
        
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')

```

## Output:
![image](https://github.com/23000285/Gaussian/assets/138970859/ffd09166-744d-4169-94d8-41132b7b68e0)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

