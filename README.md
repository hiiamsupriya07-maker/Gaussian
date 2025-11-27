# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. 1. Read n and the augmented matrix A.
2. For each pivot row i:
 * Normalize the row by dividing by the pivot
  $$A[i][i]$$
 * Eliminate entries below the pivot using   
  $$Row_k =Row_k w-A[K][i]XRow_i$$

3. Perform back substitution from the last row upward to compute each $$x_i$$.
4. Print the solutions to, t1,..., tn-1.
    

## Program:
```

Program to find the solution of a matrix using Gaussian Elimination.
n=int(input())
vals=[]
for _ in range(n*(n+1)):
    vals.append(float(input()))
a=[]
k=0
for i in range(n):
    row =[]
    for j in range(n+1):
        row.append(vals[k])
        k+=1
    a.append(row)
for i in range(n):
    pivot=a[i][i]
    for j in range(i,n+1):
        a[i][j]/= pivot
    for k in range(i+1,n):
        factor=a[k][i]
        for j in range(i,n+1):
            a[k][j]-=factor*a[i][j]
x=[0]*n
for i in range (n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]-=a[i][j]*x[j]
for i in range (n):
    print(f"X{i} = {x[i]:.2f}",end=" ")
```

## Output:
<img width="824" height="827" alt="image" src="https://github.com/user-attachments/assets/9d0ed54b-cddb-4f99-956c-3f6b5320f36d" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination without partial pivoting is written and verified using python programming.

