# NERC holiday calendar

Returns a holiday calendar for NERC, the North American Reliability
Council.

## Usage

``` r
holidayNERC(year = getRmetricsOptions("currentYear"), FinCenter = "Eastern")
```

## Arguments

- year:

  an integer value or vector of years, formatted as `YYYY`.

- FinCenter:

  a character value, the name of the financial center to use.

## Value

an object of class `"timeDate"`

## Author

Joe W. Byers

## References

http://www.nerc.com/~oc/offpeaks.html

## See also

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
[`holidayZURICH`](https://geobosh.github.io/timeDateDoc/reference/holiday-ZURICH.md)
for holidays at other major financial centers.

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
holidayNERC()
#> Eastern
#> [1] [2025-01-01] [2025-05-26] [2025-07-04] [2025-09-01] [2025-11-27]
#> [6] [2025-12-25]
holidayNERC(2008:2010)
#> Eastern
#>  [1] [2008-01-01] [2008-05-26] [2008-07-04] [2008-09-01] [2008-11-27]
#>  [6] [2008-12-25] [2009-01-01] [2009-05-25] [2009-07-04] [2009-09-07]
#> [11] [2009-11-26] [2009-12-25] [2010-01-01] [2010-05-31] [2010-07-05]
#> [16] [2010-09-06] [2010-11-25] [2010-12-25]
```
