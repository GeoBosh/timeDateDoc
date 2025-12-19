# Reverse 'timeDate' objects

Reverse a `"timeDate"` object.

## Usage

``` r
# S3 method for class 'timeDate'
rev(x)
```

## Arguments

- x:

  an object of class `"timeDate"`.

## Value

an object of class `"timeDate"`

## Examples

``` r
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
ZUR <- timeDate(dts, zone = "GMT", FinCenter = "Europe/Zurich")
ZUR
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [2004-08-30 02:00:00]
#> [4] [1990-02-09 01:00:00]
rev(ZUR)
#> Europe/Zurich
#> [1] [1990-02-09 01:00:00] [2004-08-30 02:00:00] [2001-01-15 01:00:00]
#> [4] [1989-09-28 01:00:00]
```
