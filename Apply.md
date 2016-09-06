# R Cheat Sheet : Applying functions
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [R Cheat Sheet : Applying functions](#r-cheat-sheet-applying-functions)
	- [`apply(x,index,function)`](#applyxindexfunction)
	- [`lapply(x,function)`](#lapplyxfunction)
	- [`sapply(x,function)`](#sapplyxfunction)
	- [`tapply(x,y,function)`](#tapplyxyfunction)
	- [`mapply(function,x,y,...)`](#mapplyfunctionxy)
	- [References](#references)

<!-- /TOC -->
## `apply(x,index,function)`
Applying a function to the rows (index=1) or columns (index=2) of a matrix.
```r
   > mat<-matrix(1:9,3,3)
   > mat
        [,1] [,2] [,3]
   [1,]    1    4    7
   [2,]    2    5    8
   [3,]    3    6    9
   > apply(mat,1,sum)
   [1] 12 15 18
   > apply(mat,2,sum)
   [1]  6 15 24
```
##  `lapply(x,function)`
apply a function to each element of the list x
```r
    > x<-list(1:10)
    > lapply(x,sqrt)
    [[1]]
     [1] 1.000000 1.414214 1.732051 2.000000 2.236068 2.449490 2.645751 2.828427 3.000000 3.162278
    > class(lapply(x,sqrt))
    [1] "list"
    > x
    [[1]]
     [1]  1  2  3  4  5  6  7  8  9 10
```

##  `sapply(x,function)`
apply a function to each element of the list x with simplification of result
```r
    > x<-list(1:10)
    > sapply(x,sqrt)
              [,1]
     [1,] 1.000000
     [2,] 1.414214
     [3,] 1.732051
     [4,] 2.000000
     [5,] 2.236068
     [6,] 2.449490
     [7,] 2.645751
     [8,] 2.828427
     [9,] 3.000000
    [10,] 3.162278
    > class(sapply(x,sqrt))
    [1] "matrix"
```

##  `tapply(x,y,function)`
Apply a function to subsets of a vector X and defined the subset by vector Y.
```r
    > x<-1:10
    > y <-rep(c(T,F),5)
    > tapply(x, y, sum)
    FALSE  TRUE
       30    25
    > tapply(x, y, list)
    $`FALSE`
    [1]  2  4  6  8 10

    $`TRUE`
    [1] 1 3 5 7 9

    > tapply(x, y, max)
    FALSE  TRUE
       10     9
    > class(tapply(x, y, list))
    [1] "list"
    > class(tapply(x, y, max))
    [1] "array"
```

## `mapply(function,x,y,...)`
Apply a function on multiple objects by elements. `mapply(*,x,y)` return `c(x1*y1,x2*y2,x3*y3,...)`. By default the result is simplified.

## References
* http://stackoverflow.com/questions/3505701/r-grouping-functions-sapply-vs-lapply-vs-apply-vs-tapply-vs-by-vs-aggrega
