# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program.
2. Input the order of the matrix (n) and read the augmented matrix of size n × (n+1).
3. Apply Forward Elimination:

For each pivot row i from 0 to n−1:

If the pivot element is zero, swap with a suitable row below.

For each row j below the pivot row:

Compute the ratio = a[j][i] / a[i][i].

Subtract ratio × (pivot row) from the current row to make elements below the pivot zero.
4. Display the solution vector.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: NARENDRA KRISHNAN KS
RegisterNumber: 212225240096
*/

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit("zero")
    for j in range(i+1,n):
        r=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-r*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i,x[i]),end =" ")
```

## Output:
<img width="923" height="477" alt="image" src="https://github.com/user-attachments/assets/d75cc98d-8852-4283-9da2-4af9aa3c771b" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

