# R Cheat Sheet: Basics
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [R Cheat Sheet: Basics](#r-cheat-sheet-basics)
	- [Functions, conditions and loops](#functions-conditions-and-loops)
	- [Datatypes](#datatypes)
	- [References](#references)

<!-- /TOC -->
## Functions, conditions and loops
```r
    anExampleFunction <- function(x, ...) {
        aLocalVarable <-x
        if(!is.null(x)) return(x) else message("x is null")
        while(is.null(x)) x=1
        for (i in 0:3) x=seq(1,i)
        ifelse(x%%2==0,TRUE,FALSE)
    }
```
Other stuffs:
* `break` and `next` do not return a value as they transfer control within the loop.
* `do.call(funname, args)` executes a function call from the name of the function and a list of arguments to be passed to it

## Datatypes
* vectors: `x=[1:10]` (numeric), `x=['aaa','bbbb']` (character) only one object type
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
* matrix
```r
   > matrix(seq(1,8),2,4)
     [,1] [,2] [,3] [,4]
   [1,]    1    3    5    7
   [2,]    2    4    6    8
```

* dataframe
```r
   > x<-data.frame(x = 1, y = 1:4, fac = LETTERS[1:4])
   > x
     x y fac
   1 1 1   A
   2 1 2   B
   3 1 3   C
   4 1 4   D
   > class(x$fac)
   [1] "factor"
   > x<-data.frame(x = 1, y = 1:4, fac = LETTERS[1:4],stringsAsFactors = FALSE)
   > class(x$fac)
   [1] "character"
```

## References

* https://cran.r-project.org/doc/contrib/Short-refcard.pdf
