# The names of a 'timeDate' object

Functions to get or set the names of a `"timeDate"` object.

## Usage

``` r
# S4 method for class 'timeDate'
names(x)
# S4 method for class 'timeDate'
names(x) <- value
```

## Arguments

- x:

  an object of class `"timeDate"`.

- value:

  a character vector of up to the same length as `x`, or `NULL`.

## Examples

``` r
td <- timeCalendar()
td
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]
names(td) <- LETTERS[seq_along(td)]
td
#> GMT
#>            A            B            C            D            E            F 
#> [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01] [2025-06-01] 
#>            G            H            I            J            K            L 
#> [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01] [2025-11-01] [2025-12-01] 
```
