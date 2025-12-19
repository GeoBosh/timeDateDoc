# Methods for 'is.na'

`is.na` methods for `"timeDate"` objects.

## Examples

``` r
# create a timeCalendar sequence
(td <- timeCalendar())
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]
is.na(td)
#>  [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE

# insert NA's
is.na(td) <- 2:3
td
#> GMT
#>  [1] [2025-01-01] [NA]         [NA]         [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]

# test of NA's
is.na(td)
#>  [1] FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
```
