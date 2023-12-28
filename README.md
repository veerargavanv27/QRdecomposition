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
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: VEEARRAGAVAN V
RegisterNumber: 23004739
'''
import numpy as np
def QR_Decomposition(matrix):
    # Write your code 
    a=np.array(matrix,dtype=float)
    m,n=a.shape
    q=np.zeros((m,n))
    r=np.zeros((m,n))
    for j in range(n):
        v=a[:,j]
        for i in range(j):
            r[i,j]=np.dot(q[:,i],a[:,j])
            v-=r[i,j]*q[:,i]
        r[j,j]=np.linalg.norm(v)
        q[:,j]=v/r[j,j]
    return q,r
a = np.array(eval(input()))
q,r=QR_Decomposition(a)
print(q)
print(r)
```
## Output
```
![image](https://github.com/veerargavanv27/QRdecomposition/assets/138955645/6424d565-d564-4aad-afdc-46ffa945539e))
```
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
