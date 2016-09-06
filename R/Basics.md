# R Cheat Sheet: Basics
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [R Cheat Sheet: Basics](#r-cheat-sheet-basics)
	- [Functions, conditions and loops](#functions-conditions-and-loops)
	- [Datatypes](#datatypes)
	- [Create Data](#create-data)
	- [Is it...?](#is-it)
	- [Strings](#strings)
	- [Input and output](#input-and-output)
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

## Create Data

* `seq(from,to)` generates a  sequence
```
	> seq(1,10,by=2)
	[1] 1 3 5 7 9
	> seq(1,10,length=2)
	[1]  1 10
	> seq(1,10,along=1:4)
	[1]  1  4  7 10
```

* `rep(x,n)` replicate x n times
```
	> rep(1:3,2)
	[1] 1 2 3 1 2 3
	> rep(1:3,each=2)
	[1] 1 1 2 2 3 3
```

* `runif` random unif distributed, default 0-1
```
> runif(5)
[1] 0.4490484 0.5588949 0.2798801 0.8900940 0.7158493
```

## Is it...?
`is.na(x)`, `is.null(x)`, `is.array(x)`, `is.data.frame(x)`,
`is.numeric(x)`, `is.complex(x)`, `is.character(x)`

## Strings
* `paste(...,sep=" ")` concatenate vectors after converting to character;
* `substr(x,start,stop)``
```
> substr("Hello World", 7,10)
[1] "Worl"
```
* strsplit(x,split) split x according to split
```
> strsplit("Hello World",split = " ")
[[1]]
[1] "Hello" "World"
```

* `grep(pattern,x)` searches for matches to pattern within x
```
> grep("[a-e]", letters)
 [1]  1  2  3  4  5
```
* `gsub(pattern,replacement,x)` replacement of matches to pattern
* `sub()` same as `gsub` but only replaces the first occurrence.
* `tolower(x)` convert to lowercase
* `toupper(x)` convert to uppercase
* `match(x,table)` or `x %in% table` a vector of the positions of first matches for the elements of x among table

## Input and output
* load() load the datasets written with `save`
* read.table(file) reads  a  file  in  table  format  and  creates  a  data
frame from it
	* default separator sep="" is any whitespace
	* header=TRUE read the first line as a header of column names
	* as.is=TRUE prevent character vectors from being converted to factors
	* skip=n to skip n lines before reading data
* read.csv("filename",header=TRUE)
* read.fwf(file,widths) read a table of fixed width formatted data into a ’data.frame’;
	* widths is an integer vector, giving the widths of the fixed-width fields
* save(file,...) saves the specified objects (...)  in the XDR platform-
independent binary format

## References

* https://cran.r-project.org/doc/contrib/Short-refcard.pdf
