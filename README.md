# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input matrix dimensions and initialize augmented matrix and solution vector.
2. Populate the augmented matrix with user inputs.
3. Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.
4. Back substitute to compute solution values for the variables.
5. Print the solution vector formatted to two decimal places.
 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: kavinesh k 
RegisterNumber: 26019140
*/
```

```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
n = int(input().strip())
matrix =[]
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input().strip()))
    matrix.append(row)
for i in range(n):
    for j in range(i+ 1, n):
        factor = matrix[j][i] / matrix[i][i]
        for k in range(i, n+ 1):
            matrix[j][k] -= factor * matrix[i][k]
x = [0.0] * n
for i in range(n - 1, -1, -1):
    total = sum(matrix[i][j] * x[j] for j in range(i + 1, n))
    x[i] = (matrix[i][n] - total) / matrix[i][i]
result ="".join(f"X{i} = {x[i]:.2f} " for i in range(n))
print(result)
```

## Output:

<img width="1398" height="616" alt="{2A9BEA81-AFEE-4AD6-A3AF-E6BD11A7823D}" src="https://github.com/user-attachments/assets/87713716-7d3d-4a7c-845e-a86048ba4f11" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

