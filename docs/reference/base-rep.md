# Replicating 'timeDate' objects

Replicates `"timeDate"` objects.

## Usage

``` r
# S3 method for class 'timeDate'
rep(x, ...)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- ...:

  arguments passed to the method for `'POSIXct'`,
  [`rep`](https://rdrr.io/r/base/rep.html).

## Value

an object of class `"timeDate"`

## Examples

``` r
## rep
dts = c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
ZUR = timeDate(dts, zone = "GMT", FinCenter = "Europe/Zurich")

rep(ZUR[2], times = 3)
#> Europe/Zurich
#> [1] [2001-01-15 01:00:00] [2001-01-15 01:00:00] [2001-01-15 01:00:00]
rep(ZUR[2:3], times = 2)  
#> Europe/Zurich
#> [1] [2001-01-15 01:00:00] [2004-08-30 02:00:00] [2001-01-15 01:00:00]
#> [4] [2004-08-30 02:00:00]
```
