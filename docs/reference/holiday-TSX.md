# TSX holiday calendar

Returns a holiday calendar for the Toronto Stock Exchange.

## Usage

``` r
holidayTSX(year = getRmetricsOptions("currentYear"))
```

## Arguments

- year:

  an integer value or vector of years, formatted as `YYYY`.

## Value

an object of class `"timeDate"`

## See also

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayZURICH`](https://geobosh.github.io/timeDateDoc/reference/holiday-ZURICH.md)
for holidays at other major financial centers,

[`BoxingDay`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md),
etc., for descriptions of the individual holiday functions,

[`listHolidays`](https://geobosh.github.io/timeDateDoc/reference/holiday-Listing.md)
for a list (character vector) of all holidays,

[`holiday`](https://geobosh.github.io/timeDateDoc/reference/holiday.md)
alternative to calling directly individual holiday functions (takes one
or more holiday functions as argument),

[`Easter`](https://geobosh.github.io/timeDateDoc/reference/calendar-Easter.md)

## Examples

``` r
holidayTSX()
#> Toronto
#>   2025-01-01   2025-02-17   2025-04-18   2025-05-19   2025-07-01   2025-08-04 
#> [2025-01-01] [2025-02-17] [2025-04-18] [2025-05-19] [2025-07-01] [2025-08-04] 
#>   2025-09-01   2025-10-13   2025-12-25   2025-12-26 
#> [2025-09-01] [2025-10-13] [2025-12-25] [2025-12-26] 
holidayTSX(2008:2010)
#> Toronto
#>   2008-01-01   2008-02-18   2008-03-21   2008-05-19   2008-07-01   2008-08-04 
#> [2008-01-01] [2008-02-18] [2008-03-21] [2008-05-19] [2008-07-01] [2008-08-04] 
#>   2008-09-01   2008-10-13   2008-12-25   2008-12-26   2009-01-01   2009-02-16 
#> [2008-09-01] [2008-10-13] [2008-12-25] [2008-12-26] [2009-01-01] [2009-02-16] 
#>   2009-04-10   2009-05-18   2009-07-01   2009-08-03   2009-09-07   2009-10-12 
#> [2009-04-10] [2009-05-18] [2009-07-01] [2009-08-03] [2009-09-07] [2009-10-12] 
#>   2009-12-25   2009-12-26   2010-01-01   2010-02-15   2010-04-02   2010-05-24 
#> [2009-12-25] [2009-12-28] [2010-01-01] [2010-02-15] [2010-04-02] [2010-05-24] 
#>   2010-07-01   2010-08-02   2010-09-06   2010-10-11   2010-12-25   2010-12-26 
#> [2010-07-01] [2010-08-02] [2010-09-06] [2010-10-11] [2010-12-27] [2010-12-27] 
```
