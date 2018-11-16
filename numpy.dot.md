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
- If a is an N-D array and b is an M-D array (where M>=2), it is a sum product over the last axis of a and the second-to-last axis of b:
