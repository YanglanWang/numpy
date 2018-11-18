# numpy.dot(a,b,out=None)

- If both a and b are 1-D arrays, it is inner product of vectors (without complex conjugation).
```
a = np.array([1, 2])
b = np.array([5, 6])
c=np.dot(a, b)
```
Output:
```
17
```

- If both a and b are 2-D arrays, it is matrix multiplication, but using matmul or a @ b is preferred.
```
a = np.array([[1, 2],[3,4]])
b = np.array([[5, 6],[7,8]])
c=np.dot(a,b)
d=a@b
e=np.matmul(a,b)
```
Output:
```
[[19 22]
 [43 50]]
[[19 22]
 [43 50]]
[[19 22]
 [43 50]]
```

- If either a or b is 0-D (scalar), it is equivalent to multiply and using numpy.multiply(a, b) or a * b is preferred.

- If a is an N-D array and b is a 1-D array, it is a sum product over the last axis of a and b.
```
a = np.arange(2*3*4).reshape((2,3,4))
b = np.array([5,6,1,0])
c=np.dot(a,b)
```
Output:
```
[[  8  56 104]
 [152 200 248]]
```
### In this case, b must be a 1*4 1-D array. If it doesn't have four elements, the multiplication can't accept by the system.

- If a is an N-D array and b is an M-D array (where M>=2), it is a sum product over the last axis of a and the second-to-last axis of b:
```
import numpy as np
a = np.arange(2*2*3).reshape((2,2,3))
b = np.arange(2*3*2).reshape((2,3,2))
c=np.dot(a,b)
print(c)
print(np.shape(c))
```
Output:
```
[[[[ 10  13]
   [ 28  31]]

  [[ 28  40]
   [100 112]]]


 [[[ 46  67]
   [172 193]]

  [[ 64  94]
   [244 274]]]]
(2, 2, 2, 2)

```




