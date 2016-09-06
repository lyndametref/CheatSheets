# R Cheat Sheet: Data wrangling
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [R Cheat Sheet: Data wrangling](#r-cheat-sheet-data-wrangling)
	- [Packages](#packages)
	- [Subsetting](#subsetting)
		- [Variables (columns)](#variables-columns)
		- [Observations (rows)](#observations-rows)
			- [Slicing](#slicing)
			- [Filtering](#filtering)
			- [Deduplicate](#deduplicate)
			- [Sampling](#sampling)
	- [Reshaping Data](#reshaping-data)
		- [Gather & Spread columns into row](#gather-spread-columns-into-row)
		- [Split & unitecolumn](#split-unitecolumn)
	- [Grouping, summarise and mutate](#grouping-summarise-and-mutate)
	- [Merging](#merging)
	- [Piping](#piping)
	- [References](#references)

<!-- /TOC -->

## Packages
```
library(dplyr)
library(tidyr)
```

`tbl_df(myDataframe)`
Converts data to tbl class. tbl’s are easier to examine than
data frames displays only the data that fits onscreen.
```
> tbl_df(iris)
   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
          <dbl>       <dbl>        <dbl>       <dbl>  <fctr>
1           5.1         3.5          1.4         0.2  setosa
2           4.9         3.0          1.4         0.2  setosa
3           4.7         3.2          1.3         0.2  setosa
4           4.6         3.1          1.5         0.2  setosa
5           5.0         3.6          1.4         0.2  setosa
6           5.4         3.9          1.7         0.4  setosa
7           4.6         3.4          1.4         0.3  setosa
8           5.0         3.4          1.5         0.2  setosa
9           4.4         2.9          1.4         0.2  setosa
10          4.9         3.1          1.5         0.1  setosa
... with 140 more rows
```

## Subsetting
### Variables (columns)

`select` (dplyr) Select columns by name or helper function
```
> select(iris, Sepal.Width, Petal.Length, Species)
    Sepal.Width Petal.Length    Species
1           3.5          1.4     setosa
2           3.0          1.4     setosa
3           3.2          1.3     setosa
4           3.1          1.5     setosa
5           3.6          1.4     setosa
```
helper:
* `select(iris, ends_with("Length"))`
* `select(iris, starts_with("Sepal"))`
* `select(iris, contains("."))` contains character
* `select(iris, matches(".t."))` match Regex
* `select(iris, num_range("x", 1:5))`
* `select(iris, Sepal.Length:Petal.Width)` range between 2 columns
* `select(iris, -Species)` all except specified

### Observations (rows)
#### Slicing
`slice` (dplyr) selects rows by position.
```
> slice(iris,1:5)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
```

#### Filtering
`filter` (dplyr) extracts rows that meet logical criteria on given columns
```
> filter(iris,Sepal.Length>7.6)
  Sepal.Length Sepal.Width Petal.Length Petal.Width   Species
1          7.7         3.8          6.7         2.2 virginica
2          7.7         2.6          6.9         2.3 virginica
3          7.7         2.8          6.7         2.0 virginica
4          7.9         3.8          6.4         2.0 virginica
5          7.7         3.0          6.1         2.3 virginica
```

#### Deduplicate
`distinct` (dplyr) remove duplicate rows.
```
> nrow(iris)
[1] 150
> nrow(distinct(iris))
[1] 149
```

#### Sampling
* `sample_frac(iris, 0.5, replace = TRUE)` Randomly select fraction of rows.
* `sample_n(iris, 10, replace = TRUE)` Randomly select n rows.

`replace = TRUE` Sample with replacement of elements in dataframe for subsequent choice.

## Reshaping Data

### Gather & Spread columns into row
* `gather` (tidyr) Gather columns into rows.
	* `convert` If TRUE will automatically run type.convert on the key column. This is useful if the column names are actually numeric, integer, or logical.
	* `factor_key` If FALSE, the default, the key values will be stored as a character vector. If TRUE, will be stored as a factor, which preserves the original ordering of the columns.
* `spread` (tidyr) Spread rows into columns.
```
	> test <- data.frame(Name=c("A","B","C"),M1=c(2.5,3,6),M2=c(5,6,7))
	> test
	  Name  M1 M2
	1    A 2.5  5
	2    B 3.0  6
	3    C 6.0  7
	> gather(test, Param, val, M1, M2)
	Name Param val
	1    A    M1   2.5
	2    B    M1   3.0
	3    C    M1   6.0
	4    A    M2   5.0
	5    B    M2   6.0
	6    C    M2   7.0
	> spread(gather(test,Param, val, M1,M2), Param,val)
	  Name  M1 M2
	1    A 2.5  5
	2    B 3.0  6
	3    C 6.0  7
```

### Split & unitecolumn
* `separate` (tidyr) Separate one column into several.
* `unite` (tidyr) concatenate strings of several column with a sep


```
	> test <- data.frame(
	+ id = sprintf("x%01d.%02d", c(rep(1,2),rep(2,2),rep(3,2)),rep(1:2,3)),
	+ val= runif(6))
	> test
	     id       val
	1 x1.01 0.4516309
	2 x1.02 0.1182174
	3 x2.01 0.2386353
	4 x2.02 0.4705228
	5 x3.01 0.3523231
	6 x3.02 0.3385752
	> sep <- separate(test,id, into = c("sample","replicate"))
	  sample replicate       val
	1     x1        01 0.4516309
	2     x1        02 0.1182174
	3     x2        01 0.2386353
	4     x2        02 0.4705228
	5     x3        01 0.3523231
	6     x3        02 0.3385752
	> unite(sep,id,sample,replicate,sep = "-")
	     id       val
	1 x1-01 0.4516309
	2 x1-02 0.1182174
	3 x2-01 0.2386353
	4 x2-02 0.4705228
	5 x3-01 0.3523231
	6 x3-02 0.3385752
```

## Grouping, summarise and mutate
* `mutate` create a new column from others
* `transmute` like `mutate` but drop old columns
* `summarise` summarise a column with a function
* `summarise_each` summarise all columns with a function (note use of `funs` mandatory)
* `group_by` specify by which column data should be groupped

```
> mutate(iris, Petal.Surf=Petal.Length*Petal.Width)
    Sepal.Length Sepal.Width Petal.Length Petal.Width    Species Petal.Surf
1            5.1         3.5          1.4         0.2     setosa       0.28
2            4.9         3.0          1.4         0.2     setosa       0.28
3            4.7         3.2          1.3         0.2     setosa       0.26
4            4.6         3.1          1.5         0.2     setosa       0.30
...

> transmute(iris, Petal.Surf=Petal.Length*Petal.Width)
    Petal.Surf
1         0.28
2         0.28
3         0.26
4         0.30
5         0.28
6         0.68
...

> summarise(iris,,avg=mean(Sepal.Length))
       avg
1 5.843333
> summarise_each(iris,funs(mean))
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1     5.843333    3.057333        3.758    1.199333      NA
Warning message:
In mean.default(c(1L, 1L, 1L, 1L, 1L, 1L, 1L, 1L, 1L, 1L, 1L, 1L,  :
  argument is not numeric or logical: returning NA
> iris %>% group_by(Species) %>% summarise(avg=mean(Sepal.Length))
     Species   avg
1     setosa 5.006
2 versicolor 5.936
3  virginica 6.588
```

## Merging
* `merge(a,b,all=, by=)` merge two data frames by common columns or row names, if all=TRUE, extra rows will be added to the output, one for each row in x that has no matching row in y and reciprocally
```
	> authors <- data.frame(
	     surname = I(c("Tukey", "Venables", "Tierney")),
	     deceased = c(T, rep(F, 2)))
	> books <- data.frame(
	     name = I(c("Tukey", "Venables", "Tierney",
	                "Ripley",  "R Core")),
	     title = c("Exploratory Data Analysis",
	               "Modern Applied Statistics ...",
	               "LISP-STAT",
	               "Spatial Statistics",
	               "An Introduction to R"))
	> merge(authors, books, by.x = "surname", by.y = "name", all = TRUE)
	   surname deceased                         title
	1   R Core       NA          An Introduction to R
	2   Ripley       NA            Spatial Statistics
	3  Tierney    FALSE                     LISP-STAT
	4    Tukey     TRUE     Exploratory Data Analysis
	5 Venables    FALSE Modern Applied Statistics ...
	> merge(authors, books, by.x = "surname", by.y = "name", all = FALSE)
	   surname deceased                         title
	1  Tierney    FALSE                     LISP-STAT
	2    Tukey     TRUE     Exploratory Data Analysis
	3 Venables    FALSE Modern Applied Statistics ...
```

## Piping
```
> x %>% f(y) # f(x, y)
> y %>% f(x, ., z) # f(x, y, z )
> iris %>%
   group_by(Species) %>%
   summarise(avg = mean(Sepal.Width)) %>%
   arrange(avg)
```

## References
* https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf
