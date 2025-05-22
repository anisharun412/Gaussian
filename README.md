# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## AlgorithmInput n and read the n x (n+1) augmented matrix A.

1. For each pivot row i: eliminate below by subtracting multiples of row i from rows i+1 to n-1.

2. If any pivot A[i][i] == 0, exit (division by zero).

3. After forward elimination, use back substitution:

      * Start from last row to compute X[n-1].

      * For each row i from n-2 to 0, subtract known values and divide to find X[i].

6. Print solution vector X.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Arunsamy D
RegisterNumber: 212224240016
*/
```
```python
import numpy as np
import sys

n = int(input())

arr = np.zeros((n, n+1))

scalar = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        arr[i][j] = float(input())

for i in range(n):
    if arr[i][i] == 0.0:
        sys.exit("Divide by zero detected.")
    
    for j in range(i+1,n):
        ratio = arr[j][i]/arr[i][i]
        for k in range(n+1):
            arr[j][k]  = arr[j][k]-ratio*arr[i][k]

scalar[n-1] = arr[n-1][n]/arr[n-1][n-1]

for i in range(n-2, -1, -1):
    scalar[i] = arr[i][n]
    for j in range(i+1, n):
        scalar[i] = scalar[i] - arr[i][j]*scalar[j]
    scalar[i] = scalar[i]/arr[i][i]
    
for i in range(n):
    print("X%d = %0.2f "%(i, scalar[i]), end="")


```

## Output:

![image](https://github.com/user-attachments/assets/f14921a2-adb7-4d58-8933-1d4ce6452694)

![image](https://github.com/user-attachments/assets/97b04639-51a6-4c0e-b618-f2e16ddb9d8a)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

