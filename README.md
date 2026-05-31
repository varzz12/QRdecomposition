# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import ast

A = np.array(ast.literal_eval(input()), dtype=float)

m, n = A.shape
Q = np.zeros((m, n))
R = np.zeros((n, n))

for j in range(n):
    v = A[:, j].copy()

    for i in range(j):
        R[i, j] = np.dot(Q[:, i], A[:, j])
        v = v - R[i, j] * Q[:, i]

    R[j, j] = np.linalg.norm(v)
    Q[:, j] = v / R[j, j]

print("The Q Matrix is\n", Q)
print("The R Matrix is\n", R)






```

## Output
<img width="1252" height="711" alt="image" src="https://github.com/user-attachments/assets/4888915e-0810-4bb5-beb4-21dba1c27330" />
<img width="1250" height="706" alt="image" src="https://github.com/user-attachments/assets/613d62c2-3229-4661-9645-d924dbea9d41" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
