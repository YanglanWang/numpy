# numpy.arange([start, ]stop, [step, ]dtype=None)
Return evenly spaced values within a given interval. Values are generated within the half-open interval [start, stop)

For integer arguments the function is equivalent to the Python built-in range function, 
### but returns an ndarray rather than a list.

#### When using a non-integer step, such as 0.1, the results will often not be consistent. It is better to use linspace for these cases.

- start
Start of interval. The interval includes this value. The default start value is 0.

- stop


- step
 The default step size is 1. 
 ## (not understand!) If step is specified as a position argument, start must also be given.




```
>>> np.arange(3)
array([0, 1, 2])
>>> np.arange(3.0)
array([ 0.,  1.,  2.])
>>> np.arange(3,7)
array([3, 4, 5, 6])
>>> np.arange(3,7,2)
array([3, 5])
```
