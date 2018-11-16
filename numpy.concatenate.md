# numpy.concatenate((a1, a2, ...), axis=0, out=None)
## Join a sequence of arrays along an existing axis.
### Parameters

- a1, a2, ... must have the same shape except in the dimension corresponding to axis. For example:

```
import numpy as np
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6]])
np.concatenate((a, b), axis=0)
```
Output:
```
[[1 2]
 [3 4]
 [5 6]]
```

- axis: int, optional
Default is 0. If axis is None, flattened arrays will be displayed. For example:
```
np.concatenate((a,b), axis=None)
```
Output:
```
[1 2 3 4 5 6]
```
```
np.concatenate((a,b),axis=1)
```
Output:
```
Error
```
```
np.concatenate((a,b.T),axis=1)
```
Output:
```
[[1 2 5]
 [3 4 6]]
```

- out
If provided, the destination to place the result. The shape must be correct, matching that of what concatenate would have returned if no out argument were specified.

