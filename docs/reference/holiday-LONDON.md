# London Bank Holidays

Returns bank holidays in London.

## Usage

``` r
holidayLONDON(year = getRmetricsOptions("currentYear"))
```

## Arguments

- year:

  an integer value or vector of years, formatted as `YYYY`.

## Value

an object of class `"timeDate"`.

## Details

There are currently 8 bank holidays in Britain every year: New Year's
Day, Good Friday, Easter Monday, Early Spring Holiday (first Monday of
May), Spring Holiday (Last Monday of May), Summer Holiday (Last Monday
of August), Christmas Day and Boxing Day.

Some of these holidays are referred also by alternative names or may
have had other names in the past. Also the rules according to which the
dates for some of them are calculated have changed over time.

Occasionaly there are one-off special holidays, usually related to
significant Royal events. Also as one-off, the dates of some holidays
are sometimes moved. For example, the Early spring holiday was moved
several times to 8th May to coincide with Victory day on big
anniversaries.

## Author

Original function contributed by Menon Murali; amended, corrected and
rewritten by Georgi N. Boshnakov

## See also

[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
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
holidayLONDON()
#> Europe/London
#> [1] [2025-01-01] [2025-04-18] [2025-04-21] [2025-05-05] [2025-05-26]
#> [6] [2025-08-25] [2025-12-25] [2025-12-26]
holidayLONDON(2008:2010)
#> Europe/London
#>  [1] [2008-01-01] [2008-03-21] [2008-03-24] [2008-05-05] [2008-05-26]
#>  [6] [2008-08-25] [2008-12-25] [2008-12-26] [2009-01-01] [2009-04-10]
#> [11] [2009-04-13] [2009-05-04] [2009-05-25] [2009-08-31] [2009-12-25]
#> [16] [2009-12-28] [2010-01-01] [2010-04-02] [2010-04-05] [2010-05-03]
#> [21] [2010-05-31] [2010-08-30] [2010-12-27] [2010-12-28]
```
