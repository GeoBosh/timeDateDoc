# NYSE holiday calendar

Returns a holiday (closing days) calendar for the New York Stock
Exchange.

## Usage

``` r
holidayNYSE(year = getRmetricsOptions("currentYear"), 
            type = c("", "standard", "special"))
```

## Details

`holidayNYSE` generates a list of the clossing days of the exchange for
the requested years.

The default is to return all closing days (holidays and specials).
`type = "standard"` requests only closings associated with the standard
public holidays, `type = "special"` gives the special closings only.

## Arguments

- year:

  an integer value or vector of years, formatted as `YYYY`.

- type:

  what to include, a character string. The default is to return all
  closing days (holidays and specials). `"standard"` requests only
  closings associated with the standard public holidays, `"special"`
  gives the special closings only.

## Note

The list of closing days returned by `holidayNYSE` was changed in
timeDate version 4021.105, in that previously it did not include special
closing days. This was perceived by some users as buggy. Also, the
intent by the authors of the package seems to have been for it to return
all closing days. Indeed, the default for `isisBizday()` is to drop
weekends and days returned by `holidayNYSE`.

Argument `type` was also included in version 4021.105. The old behaviour
can be obtained by using `type = "standard"`.

The default for argument `type` is currently the empty string, since I
couldn't come up with another string that would be universally easy to
remember. Suggestions are welcome but a change will be only feasible if
they come soon.

## Author

Diethelm Wuertz (original author); Yohan Chalabi improved speed and
handling of time zone; Georgi N. Boshnakov added the special closings
and argument ‘type’.

## Value

an object of class `"timeDate"`

## See also

[`earlyCloseNYSE`](https://geobosh.github.io/timeDateDoc/reference/earlyCloseNYSE.md)
for times of early closings of NYSE,

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
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
holidayNYSE()  # current year
#> NewYork
#>  [1] [2025-01-01] [2025-01-20] [2025-02-17] [2025-04-18] [2025-05-26]
#>  [6] [2025-06-19] [2025-07-04] [2025-09-01] [2025-11-27] [2025-12-25]
holidayNYSE(2008:2010)
#> NewYork
#>  [1] [2008-01-01] [2008-01-21] [2008-02-18] [2008-03-21] [2008-05-26]
#>  [6] [2008-07-04] [2008-09-01] [2008-11-27] [2008-12-25] [2009-01-01]
#> [11] [2009-01-19] [2009-02-16] [2009-04-10] [2009-05-25] [2009-07-03]
#> [16] [2009-09-07] [2009-11-26] [2009-12-25] [2010-01-01] [2010-01-18]
#> [21] [2010-02-15] [2010-04-02] [2010-05-31] [2010-07-05] [2010-09-06]
#> [26] [2010-11-25] [2010-12-24]

## January 2, 2007 was a memorial day for president G.R. Ford,
##    not a regular public holiday
holidayNYSE(2007)
#> NewYork
#>  [1] [2007-01-01] [2007-01-02] [2007-01-15] [2007-02-19] [2007-04-06]
#>  [6] [2007-05-28] [2007-07-04] [2007-09-03] [2007-11-22] [2007-12-25]
holidayNYSE(2007, type = "standard")
#> NewYork
#> [1] [2007-01-01] [2007-01-15] [2007-02-19] [2007-04-06] [2007-05-28]
#> [6] [2007-07-04] [2007-09-03] [2007-11-22] [2007-12-25]
holidayNYSE(2007, type = "special")
#> New_York
#> [1] [2007-01-02]
```
