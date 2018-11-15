In scipy.org
> - If both arguments are 2-D they are multiplied like conventional matrices.
> - If either argument is N-D, N > 2, it is treated as a stack of matrices residing in the last two indexes and broadcast accordingly.
> - If the first argument is 1-D, it is promoted to a matrix by prepending a 1 to its dimensions. After matrix multiplication the prepended 1 is removed.
> - If the second argument is 1-D, it is promoted to a matrix by appending a 1 to its dimensions. After matrix multiplication the appended 1 is removed.

The first rule is very simple for understanding. 

For second rule: we can do the matrix multiplication based on the last two indexes. If the other indexes except the last two indexes are different, the system will use broadcast accordingly, in other words, the smaller matrix will add the same sub-matrixes composed of only last two indexes to the lacking position compared with the larger matrix.

For third and fourth rules, suppose one of the argument is 1-D with m elements. If this argument is the first one, it is changed to shape of (1,m) 2-D matrix. If this argument is the second one, it is changed into shape of (m,1) 2-D matrix.

