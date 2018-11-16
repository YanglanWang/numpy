# numpy.random.randn(d0, d1,..., dn)
> It generates an array of shape(d0, d1,...,dn), filling with random floats sampled from a univariate “normal” (Gaussian) distribution of mean 0 and variance 1 (if any of the d_i are floats, they are first converted to integers by truncation, such as changing 2.9 to 2).
> If no arguments are provided, randn returns a single float.

For random samples from ![equation1](http://latex.codecogs.com/gif.latex?%5Cmathbb%7BN%7D%5Cleft%20%28%20%5Cmu%20%2C%20%5Csigma%20%5E%7B2%7D%20%5Cright%20%29), use:

![sigma](http://latex.codecogs.com/gif.latex?%5Csigma) * np.random.randn(...) + ![mu](http://latex.codecogs.com/gif.latex?%5Cmu)

```
np.random.randn()
```

2.1923875335537315 #random


Two-by-four array of samples from N(3, 6.25):

```
2.5 * np.random.randn(2, 4) + 3
```

array([[-4.49401501,  4.00950034, -1.81814867,  7.29718677],  #random
       [ 0.39924804,  4.68456316,  4.99394529,  4.84057254]]) #random
       
       
