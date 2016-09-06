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

*`break` and `next` do not return a value as they transfer control within the loop.
```r
do.call(funname, args) ##executes a function call from the name of the function and a list of arguments to be passed to it
```
## References

* https://cran.r-project.org/doc/contrib/Short-refcard.pdf