# Lagged 'timeDate' differences

Returns suitably lagged and iterated differences.

## Usage

``` r
# S3 method for class 'timeDate'
diff(x, lag = 1, differences = 1, ...)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- lag:

  an integer indicating which lag to use.

- differences:

  an integer indicating the order of the difference.

- ...:

  arguments passed to other methods.

## Value

if `x` is a vector of length `n` and `differences=1`, then the computed
result is equal to the successive differences
`x[(1+lag):n] - x[1:(n-lag)]`. If `difference` is larger than one this
algorithm is applied recursively to `x`. Note that the returned value is
a vector which is shorter than `x`.

## See also

[`difftimeDate`](https://geobosh.github.io/timeDateDoc/reference/base-difftimeDate.md)
for the difference of two `"timeDate"` objects.

## Examples

``` r
## create character vectors
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55",   "10:34:02",   "08:30:00",   "11:18:23")
## timeDate
GMT <- timeDate(dts, zone = "GMT", FinCenter = "GMT") + 24*3600
GMT
#> GMT
#> [1] [1989-09-29] [2001-01-16] [2004-08-31] [1990-02-10]

## suitably lagged and iterated differences
diff(GMT)
#> Time differences in days
#> [1]  4127  1323 -5316
diff(GMT, lag = 2)
#> Time differences in days
#> [1]  5450 -3993
diff(GMT, lag = 1, diff = 2)
#> Time differences in days
#> [1] -2804 -6639
```
