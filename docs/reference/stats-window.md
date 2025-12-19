# Time windows

Extract the subset of a `"timeDate"` object observed between two time
stamps.

## Usage

``` r
# S3 method for class 'timeDate'
window(x, start , end, ...)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- start, end:

  starting date, required, and end date, optional. If supplied `to` must
  be after `from`.

- ...:

  arguments passed to other methods.

## Value

an object of class `"timeDate"`

## Examples

``` r
## timeCalendar
# monthly dates in current year
tS = timeCalendar()
tS 
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]
   
## window
# 2nd quarter window:
tS[4:6]
#> GMT
#> [1] [2025-04-01] [2025-05-01] [2025-06-01]
window(tS, tS[4], tS[6])
#> GMT
#> [1] [2025-04-01] [2025-05-01] [2025-06-01]
```
