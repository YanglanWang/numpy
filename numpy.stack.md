# numpy.stack(arrays, axis=0, out=None)
join a sequence of arrays along a new axis

> arrays must have same shapes
>
> The axis parameter specifies the index of the new axis in the dimensions of the result. For example, if axis=0 it will be the first dimension and if axis=-1 it will be the last dimension.
>
> out : ndarray, optional
>
> If provided, the destination to place the result. The shape must be correct, matching that of what stack would have returned if no out argument were specified.

## Examples:

```
a=arrays = [np.random.randn(3, 4) for _ in range(2)]
print(a)
b=np.stack(a,axis=0)
print(b)
print(np.shape(b))
c=np.stack(a,axis=1)
print(c)
print(np.shape(c))
d=np.stack(a,axis=2)
print(d)
print(np.shape(d))
```

```
[array([[ 0.83884083, -1.43215605,  1.41533665, -0.00716332],
       [ 0.46544822,  0.34907277,  1.31252218,  0.26188573],
       [-0.0512045 , -1.46566467, -1.57198227, -0.26868876]]), 

array([[-1.42819468,  0.33949845, -0.55079505, -0.28101863],
       [ 2.04869521, -0.83523424,  0.40519545, -1.6959958 ],
       [ 2.21329892,  0.91438675, -1.13832543, -0.81822325]])]
       
[[[ 0.83884083 -1.43215605  1.41533665 -0.00716332]
  [ 0.46544822  0.34907277  1.31252218  0.26188573]
  [-0.0512045  -1.46566467 -1.57198227 -0.26868876]]

 [[-1.42819468  0.33949845 -0.55079505 -0.28101863]
  [ 2.04869521 -0.83523424  0.40519545 -1.6959958 ]
  [ 2.21329892  0.91438675 -1.13832543 -0.81822325]]]
(2, 3, 4)

[[[ 0.83884083 -1.43215605  1.41533665 -0.00716332]
  [-1.42819468  0.33949845 -0.55079505 -0.28101863]]

 [[ 0.46544822  0.34907277  1.31252218  0.26188573]
  [ 2.04869521 -0.83523424  0.40519545 -1.6959958 ]]

 [[-0.0512045  -1.46566467 -1.57198227 -0.26868876]
  [ 2.21329892  0.91438675 -1.13832543 -0.81822325]]]
(3, 2, 4)

[[[ 0.83884083 -1.42819468]
  [-1.43215605  0.33949845]
  [ 1.41533665 -0.55079505]
  [-0.00716332 -0.28101863]]

 [[ 0.46544822  2.04869521]
  [ 0.34907277 -0.83523424]
  [ 1.31252218  0.40519545]
  [ 0.26188573 -1.6959958 ]]

 [[-0.0512045   2.21329892]
  [-1.46566467  0.91438675]
  [-1.57198227 -1.13832543]
  [-0.26868876 -0.81822325]]]
(3, 4, 2)
```

## So, I think if the problem needs some changes about the matrix(mostly in dealing with raw data), the np.stack(array,axis)can be used.
