# numpy.matmul(a, b, out=None)
matrix product of two arrays
Multiplication by a scalar is not allowed, use array*scalar instead.

## parameters
> out : ndarray, optional
> Output argument. This must have the exact kind that would be returned if it was not used. In particular, it must have the right type, must be C-contiguous, and its dtype must be the dtype that would be returned for dot(a,b). This is a performance feature. Therefore, if these conditions are not met, an exception is raised, instead of attempting to be flexible.

## Returns
> Returns the dot product of a and b. If a and b are both 1-D arrays then a scalar is returned; otherwise an array is returned. If out is given, then it is returned.

## Raises
> value Error: If the last dimension of a is not the same size as the second-to-last dimension of b. Or if scalar value is passed.


> - If both arguments are 2-D they are multiplied like conventional matrices.
> - If either argument is N-D, N > 2, it is treated as a stack of matrices residing in the last two indexes and broadcast accordingly.
> - If the first argument is 1-D, it is promoted to a matrix by prepending a 1 to its dimensions. After matrix multiplication the prepended 1 is removed.
> - If the second argument is 1-D, it is promoted to a matrix by appending a 1 to its dimensions. After matrix multiplication the appended 1 is removed.

The first rule is very simple for understanding, such as:
```
import numpy as np
a=np.array([[1,2],[3,4]])
b=np.array([[4,2],[0,1]])
c=np.matmul(a,b)
c
```
Output
```
array([[ 4,  4],
       [12, 10]])
```
For second rule: we can do the matrix multiplication based on the last two indexes. If the other indexes except the last two indexes are different, the system will use broadcast accordingly, in other words, the smaller matrix will add the same sub-matrixes composed of only last two indexes (see the submatrix as element) to reach the other dimensions indicated by the larger matrix.

```
import numpy as np
a = np.arange(2*2*4).reshape((2,2,4))
b = np.arange(2*2*4).reshape((2,4,2))
np.matmul(a,b)
np.shape(np.matmul(a,b))
```
Output:
```
array([[[ 28,  34],
        [ 76,  98]],

       [[428, 466],
        [604, 658]]])
(2, 2, 2)
```

when broadcasting happened:
```
import numpy as np
a = np.arange(2*2*4).reshape((2,2,4))
b = np.arange(1*2*4).reshape((1,4,2))
np.shape(np.matmul(a,b))
np.matmul(a,b)
```
Output:
```
array([[[ 28,  34],
        [ 76,  98]],

       [[124, 162],
        [172, 226]]])
(2, 2, 2)
```

For third and fourth rules, suppose one of the argument is 1-D with m elements. If this argument is the first one, it is changed to shape of (1,m) 2-D matrix. If this argument is the second one, it is changed into shape of (m,1) 2-D matrix.
```
import numpy as np
a=np.array([[1,2],[3,4],[5,6]])
b=np.array([1,0])
c=np.matmul(a,b)
c
```
Output:
```
array([1, 3, 5])
```
If b is a 1-D array with more than 2 elements or just one element, the system will return error.

```
import numpy as np
a=np.array([[1,2],[3,4],[5,6]])
b=np.array([1,0,1])
c=np.matmul(b,a)
c
```
Output
```
array([6, 8])
```


