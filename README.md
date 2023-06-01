# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
## Step 1:
Intialize the matrix Q and u
## Step 2:
The vector u and e is given by

   ![1](https://github.com/Vanitha-SM/QRdecomposition/assets/119557985/b43a412b-ba48-49a7-939a-cd50e781534f)

   ![ex6](https://github.com/Vanitha-SM/QRdecomposition/assets/119557985/617c1e1e-c23b-4e5b-8d34-fa8b6bd69d80)

   ![ex3](https://github.com/Vanitha-SM/QRdecomposition/assets/119557985/8f88a4e3-8b4f-4908-89bc-5feb0fbd6f4a)


## Step 3:
Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
## Step 4:
Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Vanitha S
RegisterNumber: 212222100057
'''
import numpy as np
def QR_Decomposition(A):
    n, m=A.shape
    Q = np.empty((n, n))
    u = np.empty((n, n))
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1,n):
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j] * Q[:, j])
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
    R = np.zeros((n,m))    
    for i in range(n):
        for j in range(i, m):
            R[i ,j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)    
    
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
```
![image](https://github.com/Vanitha-SM/QRdecomposition/assets/119557985/3394ffc2-6b83-41f5-b01c-bb912d206073)

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
