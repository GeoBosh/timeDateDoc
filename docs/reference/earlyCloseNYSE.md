# Early closings of the New York Stock exchange

Get dates of early closings of the New York Stock exchange (NYSE).

## Usage

``` r
earlyCloseNYSE(year)
```

## Arguments

- year:

  a vector of integers representing years (4 digits).

## Details

`earlyCloseNYSE` gives the dates and times when NYSE was closed early.
Some of these closing are scheduled (e.g. at 1pm on the day before or
after a holiday), others are unscheduled.

The information is incomplete, particularly after 2011. For those dates
the values are computed using explicitly declared rules or, if not
available, ones derived from recent years.

## Value

a `"timeDate"` object containing the dates (with closing times) of early
closings

## References

https://archive.fo/XecDq

## Author

Georgi N. Boshnakov

## Note

The function is somewhat experimental but the type of the result will
not change.

## See also

[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md)
for a list of NYSE holidays

## Examples

``` r
earlyCloseNYSE(1990)
#> GMT
#> [1] [1990-07-03 13:00:00] [1990-11-23 13:00:00] [1990-12-24 13:00:00]
#> [4] [1990-12-24 14:00:00]

earlyCloseNYSE(2022:2024) # early closings
#> GMT
#> [1] [2022-11-25 13:00:00] [2023-07-03 13:00:00] [2023-11-24 13:00:00]
#> [4] [2024-07-03 13:00:00] [2024-11-29 13:00:00] [2024-12-24 13:00:00]
holidayNYSE(2022:2024)    # holidays
#> NewYork
#>  [1] [2022-01-17] [2022-02-21] [2022-04-15] [2022-05-30] [2022-06-20]
#>  [6] [2022-07-04] [2022-09-05] [2022-11-24] [2022-12-26] [2023-01-02]
#> [11] [2023-01-16] [2023-02-20] [2023-04-07] [2023-05-29] [2023-06-19]
#> [16] [2023-07-04] [2023-09-04] [2023-11-23] [2023-12-25] [2024-01-01]
#> [21] [2024-01-15] [2024-02-19] [2024-03-29] [2024-05-27] [2024-06-19]
#> [26] [2024-07-04] [2024-09-02] [2024-11-28] [2024-12-25]
## early closings & holidays combined
c(earlyCloseNYSE(2022:2024), holidayNYSE(2022:2024))
#> GMT
#>  [1] [2022-11-25 13:00:00] [2023-07-03 13:00:00] [2023-11-24 13:00:00]
#>  [4] [2024-07-03 13:00:00] [2024-11-29 13:00:00] [2024-12-24 13:00:00]
#>  [7] [2022-01-17 05:00:00] [2022-02-21 05:00:00] [2022-04-15 04:00:00]
#> [10] [2022-05-30 04:00:00] [2022-06-20 04:00:00] [2022-07-04 04:00:00]
#> [13] [2022-09-05 04:00:00] [2022-11-24 05:00:00] [2022-12-26 05:00:00]
#> [16] [2023-01-02 05:00:00] [2023-01-16 05:00:00] [2023-02-20 05:00:00]
#> [19] [2023-04-07 04:00:00] [2023-05-29 04:00:00] [2023-06-19 04:00:00]
#> [22] [2023-07-04 04:00:00] [2023-09-04 04:00:00] [2023-11-23 05:00:00]
#> [25] [2023-12-25 05:00:00] [2024-01-01 05:00:00] [2024-01-15 05:00:00]
#> [28] [2024-02-19 05:00:00] [2024-03-29 04:00:00] [2024-05-27 04:00:00]
#> [31] [2024-06-19 04:00:00] [2024-07-04 04:00:00] [2024-09-02 04:00:00]
#> [34] [2024-11-28 05:00:00] [2024-12-25 05:00:00]
```
