# Zurich holiday calendar

Returns a holiday calendar for Zurich.

## Usage

``` r
holidayZURICH(year = getRmetricsOptions("currentYear"))
```

## Arguments

- year:

  an integer value or vector of years, formatted as `YYYY`.

## Details

The Zurich holiday calendar includes the following holidays:
NewYearsDay, GoodFriday, EasterMonday, LaborDay, PentecostMonday,
ChristmasDay, BoxingDay, CHBerchtoldsDay, CHSechselaeuten, CHAscension,
CHConfederationDay, CHKnabenschiessen.

## See also

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
for holidays at other major financial centers,

[`BoxingDay`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md),
etc., for descriptions of the individual holiday functions,

[`listHolidays`](https://geobosh.github.io/timeDateDoc/reference/holiday-Listing.md)
for a list (character vector) of all holidays,

[`holiday`](https://geobosh.github.io/timeDateDoc/reference/holiday.md)
alternative to calling directly individual holiday functions (takes one
or more holiday functions as argument),

[`Easter`](https://geobosh.github.io/timeDateDoc/reference/calendar-Easter.md)

## Value

an object of class `"timeDate"`

## Examples

``` r
holidayZURICH()
#> Zurich
#>  [1] [2025-01-01] [2025-01-02] [2025-04-18] [2025-04-21] [2025-04-21]
#>  [6] [2025-05-01] [2025-05-29] [2025-06-09] [2025-08-01] [2025-09-08]
#> [11] [2025-12-25] [2025-12-26]
holidayZURICH(2008:2010)
#> Zurich
#>  [1] [2008-01-01] [2008-01-02] [2008-03-21] [2008-03-24] [2008-04-21]
#>  [6] [2008-05-01] [2008-05-01] [2008-05-12] [2008-08-01] [2008-09-08]
#> [11] [2008-12-25] [2008-12-26] [2009-01-01] [2009-01-02] [2009-04-10]
#> [16] [2009-04-13] [2009-04-20] [2009-05-01] [2009-05-21] [2009-06-01]
#> [21] [2009-09-14] [2009-12-25] [2010-01-01] [2010-04-02] [2010-04-05]
#> [26] [2010-04-19] [2010-05-13] [2010-05-24] [2010-09-13]
```
