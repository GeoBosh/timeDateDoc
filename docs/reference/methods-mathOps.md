# Mathematical operations with 'timeDate' objects

Functions for mathematical and logical operations on `"timeDate"`
objects.

## Usage

``` r
# S4 method for class 'timeDate,timeDate'
Ops(e1, e2)
```

## Arguments

- e1, e2:

  objects of class `"timeDate"`. In the case of addition and subtraction
  one of them may be of class `numeric`, specifying the number of
  seconds to add or subtract.

## Details

Group `"Ops"` represents the binary mathematical operators. Methods are
defined for such operations when one or both arguments are from class
`"timeDate"`.

Operations that don't make sense, such as addition of two `"timeDate"`
objects, throw error.

The plus operator `"+"` performs arithmetic "+" operation on
`"timeDate"` objects,

and the minus operator `"-"` returns a `difftime` object if both
arguments `e1` and `e2` are `"timeDate"` objects, or returns a
`"timeDate"` object `e2` seconds earlier than `e1`.

## Value

addition of numeric to `"timeDate"` returns `"timeDate"`,

subtraction of numeric from `"timeDate"` returns `"timeDate"`,

subtraction of two `"timeDate"` objects returns `"difftime"`,

other operations between two `"timeDate"` objects are applied to the
underlying times (slot `"Date"`). The result of that operation is
converted to `"timeDate"` if it represents a time and returned as is
otherwise.

## Examples

``` r
## create some data
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55",   "10:34:02",   "08:30:00",   "11:18:23")
GMT <- timeDate(dts, zone = "GMT", FinCenter = "GMT")
ZUR <- timeDate(dts, zone = "GMT", FinCenter = "Europe/Zurich")
   
## add one day 
GMT + 24*3600
#> GMT
#> [1] [1989-09-29] [2001-01-16] [2004-08-31] [1990-02-10]

## subtract
ZUR[2] - ZUR[1] 
#> Time difference of 4127 days
```
