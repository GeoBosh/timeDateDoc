# Coercion from 'timeDate' to other classes

Coerce and transform objects of class `"timeDate"`.

## Usage

``` r
# S3 method for class 'timeDate'
as.character(x, ...)

# S3 method for class 'timeDate'
as.double(x, 
    units = c("auto", "secs", "mins", "hours", "days", "weeks"), ...)

# S3 method for class 'timeDate'
as.data.frame(x, ...)

# S3 method for class 'timeDate'
as.POSIXct(x, tz = "", ...)

# S3 method for class 'timeDate'
as.POSIXlt(x, tz = "", ...)

# S3 method for class 'timeDate'
as.Date(x, method = c("trunc", "round", "next"), ...)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- units:

  a character string denoting the date/time units in which the results
  are desired.

- tz:

  inputs the time zone to POSIX objects, i.e. the time zone, `zone`, or
  financial center string, `FinCenter`, as used by `"timeDate"` objects.

- method:

  a character string denoting the method how to determine the dates.

- ...:

  arguments passed to other methods.

## Value

an object from the designated target class

## See also

[`timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md)
and
[`as.timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md)
for creation of and conversion to `"timeDate"` objects

## Examples

``` r
## timeDate
tC = timeCalendar()

## convert 'timeDate' to a character vector
as.character(tC)
#>  [1] "2025-01-01" "2025-02-01" "2025-03-01" "2025-04-01" "2025-05-01"
#>  [6] "2025-06-01" "2025-07-01" "2025-08-01" "2025-09-01" "2025-10-01"
#> [11] "2025-11-01" "2025-12-01"
```
