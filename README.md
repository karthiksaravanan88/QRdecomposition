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
    import numpy as np
    def QR_Decomposition(A):
        n,m=A.shape
        Q=np.empty((n,n))
        u=np.empty((n,n))
        u[:,0]=A[:,0]
        Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
        for i in range(1,n):
            u[:,i]=A[:,i]
            for j in range(i):
                u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
            Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
        R=np.zeros((n,m))        
        for i in range(n):
            for j in range(i,m):
                R[i,j]=A[:,j]@Q[:,i]
        print("The Q Matrix is \n",Q)        
        print("The R Matrix is \n",R)
    a=np.array(eval(input()))    
    QR_Decomposition(a)






```

## Output
```
![Screenshot 2024-12-21 204005](https://github.com/user-attachments/assets/abf6f53e-881c-4c59-bee3-75ce3efbd444)

```
![Screenshot 2024-12-21 204855](https://github.com/user-attachments/assets/0e9327c1-6a65-43e2-a46a-e3de3b67f21e)
![Screenshot 2024-12-21 204855](https://github.com/user-attachments/assets/7078fe93-15a9-4444-93d1-01910f63d676)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
