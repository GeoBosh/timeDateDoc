# Set operations on timeInterval objects

Union, intersection, complement and set difference of `"timeInterval"`
objects. Also testing if an object is in a `"timeInterval"` and `tiInf`
representing the infinite time interval.

## Usage

``` r
# S3 method for class 'timeInterval'
!x
# S4 method for class 'timeInterval,timeInterval'
e1 & e2
# S4 method for class 'timeInterval,timeInterval'
e1 | e2
# S4 method for class 'timeInterval,timeInterval'
e1^e2

x %in_int% ti
# S4 method for class 'timeInterval,timeInterval'
x %in_int% ti
# S4 method for class 'timeDate,timeInterval'
x %in_int% ti

tiInf
```

## Arguments

- x:

  a `"timeInterval"` or `"timeDate"` object

- e1,e2,ti:

  `"timeInterval"` objects

## Details

Let `ti1` and `ti2` be objects from class `"timeInterval"`.

`ti1 & ti2` is the intersection of `ti1` and `ti2`, `ti1 | ti2` their
union, `ti1` the complement of `ti1` (w.r.t. `(-Inf, Inf)`).

`ti1 ^ ti2` is the complement of `ti1` w.r.t. `ti2`, i.e., the set
difference `ti2`/`ti1` (all points in `ti2` that are not in `ti1`).
`!ti1` is the same as `ti1 ^ timeInterval(left = -Inf, right = Inf)`.

`tiInf` represents the time interval from `-Inf` to `Inf`.

A motivation for using the logical operators for set operations is that
in mathematics the notation for them is similar and the properties of
logical ‘and’, ‘or’ and ‘negation’ are analogous to those of
intersection, union and complement. Also \\A^c\\ is one of the notations
for complement, where ‘c’ stands for the universe (the whole set w.r.t.
which the complement is taken). Here, it corresponds to
`timeInterval(left = -Inf, right = Inf)`. We extend this notation to
allow taking a complement w.r.t. any `"timeInterval"` (i.e., a set
difference).

`x %in_int% ti` checks if `x` is in the `"timeInterval"` `ti`.

If `x` is a `"timeInterval"` object, the result of `x %in_int% ti` is a
single `TRUE` value if `x` is a sub-interval of `ti`; `FALSE` otherwise.

If `x` is a `"timeDate"` object, the result of `x %in_int% ti` is a
logical vector indicating which times are in `ti`.

## Value

for `"&"`, `"|"`, `"!"` and `"^"` methods - a `"timeInterval"` object,

## Author

Georgi N. Boshnakov

## See also

class
`"`[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-class.md)`"`,

[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-methods.md)
for creation of `"timeInterval"` objects and further examples,

`in_int` for set operations on `"timeInterval"` objects

## Examples

``` r
## create a time interval by rounding to the enclosing hour
ti <- timeInterval(timeDate("2024-12-20 10:20:30"), unit = "hours")
ti
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-20 11:00:00)

## a similar interval on the following day
tib <- timeInterval(timeDate("2024-12-21 10:20:30"), unit = "hours")
tib
#> simple time interval
#> GMT
#> [2024-12-21 10:00:00 -- 2024-12-21 11:00:00)

ti2 <- ti | tib
ti2
#> union of 2 time intervals
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-20 11:00:00)
#> [2024-12-21 10:00:00 -- 2024-12-21 11:00:00)

ti & ti2
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-20 11:00:00)
ti | ti2
#> union of 2 time intervals
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-20 11:00:00)
#> [2024-12-21 10:00:00 -- 2024-12-21 11:00:00)

!ti
#> union of 2 time intervals
#> GMT
#> [-Inf -- 2024-12-20 10:00:00)
#> [2024-12-20 11:00:00 -- Inf)
!ti2
#> union of 3 time intervals
#> GMT
#> [-Inf -- 2024-12-20 10:00:00)
#> [2024-12-20 11:00:00 -- 2024-12-21 10:00:00)
#> [2024-12-21 11:00:00 -- Inf)

identical(!ti, ti ^ timeInterval(left = -Inf, right = Inf))
#> [1] TRUE
identical(!ti2, ti2 ^ timeInterval(left = -Inf, right = Inf))
#> [1] TRUE

## tiInf represents the time interval (-Inf, Inf)
identical(tiInf, timeInterval(left = -Inf, right = Inf))
#> [1] FALSE

ti ^ ti2 # ti2 \ ti
#> simple time interval
#> GMT
#> [2024-12-21 10:00:00 -- 2024-12-21 11:00:00)
ti2 ^ ti # ti  \ ti2
#> GMT
#> An empty timeInterval 

timeDate("2024-12-20 10:20:30") %in_int% ti2  # TRUE
#> [1] TRUE
timeDate("2024-12-20 11:20:30") %in_int% ti2  # FALSE
#> [1] FALSE

timeDate(c("2024-12-20 10:20:30", "2024-12-20 11:20:30")) %in_int% ti2  
#> [1]  TRUE FALSE

## ti's are closed on the left and open on the right, hence:
ti2@left %in_int% ti2    # [1] TRUE TRUE
#> [1] TRUE TRUE
ti2@right %in_int% ti2   # [1] FALSE FALSE
#> [1] FALSE FALSE

## a timeInterval is a scalar, so the following give a single TRUE/FALSE
## indicating whether or not the first interval is contained in the second
ti %in_int% ti2
#> [1] TRUE
ti2 %in_int% ti
#> [1] FALSE
```
