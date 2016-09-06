# R Cheat Sheet: Basics

## Functions, conditions and loops
```r
    aExampleFunction <- function(x, ...) {
        aLocalVarable <-x
        if(!is.null(x)) return(x) else message("x is null")
        for (i in [0:10]) message("x is null")
        while(is.null(x)) x=x+1
        ifelse(x==1,message("x is 1"),message("x is not 1"))
        x
    }
```

Other stuffs:

* `break` and `next` do not return a value as they transfer control within the loop.
* `do.call(funname, args)` executes a function call from the name of the function and a list of arguments to be passed to it

## Datatypes
* vectors: `x=[1:10]`, `x=['aaa','bbbb']`, `x=[1.2,2.5]` only one object type
* list: Lists have elements, each of which can contain any type of R object
```r
    > mylist<-list(x='a',y=2,z=1:10,n='Hello world')
    > mylist[1]
    $x
    [1] "a"
    > mylist[[1]]
    [1] "a"
    > mylist["z"]
    $z
    [1]  1  2  3  4  5  6  7  8  9 10
    > mylist$n
    [1] "Hello world"
```

## Applying function
* `apply(X,INDEX,FUN=)` return a vector or array or list of values obtained by applying a function FUN to margins (INDEX) of X
* `lapply(X,FUN)` apply FUN to each element of the list X 
* `sapply(X,FUN)` apply FUN to each element of the list X with simplificationof result
* `tapply(X,INDEX,FUN=)` apply FUN to each cell of a ragged array given by X with indexes INDEX

## Data wrangling
* `merge(a,b,all=, by)` merge two data frames by common columns or row names, if all=TRUE, extra rows will be added to the output, one for each row in x that has no matching row in y and reciprocally



## References

* https://cran.r-project.org/doc/contrib/Short-refcard.pdf