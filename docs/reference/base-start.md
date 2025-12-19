# Terminal times and range

Extracts the time when the first or last observation was taken, or
computes the range of the dates in a `"timeDate"` object.

## Usage

``` r
# S3 method for class 'timeDate'
start(x, ...)

# S3 method for class 'timeDate'
end(x, ...)

# S3 method for class 'timeDate'
min(..., na.rm = FALSE)

# S3 method for class 'timeDate'
max(..., na.rm = FALSE)

# S3 method for class 'timeDate'
range(..., na.rm = FALSE)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- ...:

  ignored by `start` and `end`; a 'timeDate' object for `min`, `max`,
  and `range`.

- na.rm:

  not used.

## Details

Conceptually, the `"timeDate"` object is sorted before the computations.
In particular, `start` is not necessarilly the first element of the
object and similarly for the other functions.

`min` and `max` are equivalent to `start` end `end`, respectively.

`range` returns the earlies and the latest times in a `"timeDate"`
object. The remaining functions return only one of them, as suggested by
their names.

## Value

an object of class `"timeDate"`

## Examples

``` r
## timeCalendar
# Random Calendar Dates:
tR = sample(timeCalendar())
sort(tR)
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]
tR
#> GMT
#>  [1] [2025-12-01] [2025-10-01] [2025-06-01] [2025-05-01] [2025-04-01]
#>  [6] [2025-07-01] [2025-01-01] [2025-09-01] [2025-02-01] [2025-08-01]
#> [11] [2025-11-01] [2025-03-01]
    
## start | end
start(tR)
#> GMT
#> [1] [2025-01-01]
end(tR)
#> GMT
#> [1] [2025-12-01]
   
## the first and last time stamp
tR[1]
#> GMT
#> [1] [2025-12-01]
tR[length(tR)]
#> GMT
#> [1] [2025-03-01]
rev(tR)[1]
#> GMT
#> [1] [2025-03-01]
   
## the range
c(start(tR), end(tR))
#> GMT
#> [1] [2025-01-01] [2025-12-01]
range(tR)
#> GMT
#> [1] [2025-01-01] [2025-12-01]
```
