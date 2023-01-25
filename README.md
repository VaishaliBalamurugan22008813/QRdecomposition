# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![image](https://user-images.githubusercontent.com/119390134/214597811-c78a6af6-4777-4829-a578-4d4bb4e5af11.png)

3.	Obtain the Q matrix   
   ![image](https://user-images.githubusercontent.com/119390134/214598060-cbc55e4f-ffaa-4d7c-8ead-30d9f8559112.png)
4.	Construct the upper triangular matrix R
    

## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: VAISHALI BALAMUURGAN
RegisterNumber: 22008813
import numpy as np
def QR_Decomposition(A):
n, m = A.shape
Q = np.empty((n, n))
u = np.empty((n, n))
u[:, 0] = A[:, 0]
Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
for i in range(1, n):
u[:, i] = A[:, i]
for j in range(i):
u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
R = np.zeros((n, m))
for i in range(n):
for j in range(i, m):
R[i, j] = A[:, j] @ Q[:, i]
print(Q)
print(R)
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
![image](https://user-images.githubusercontent.com/119390134/214598713-3f115db0-f38e-4a28-9e62-14cbeac49f6a.png)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
