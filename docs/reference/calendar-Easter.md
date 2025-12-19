# Date of Easter

Returns the date of Easter.

## Usage

``` r
Easter(year = getRmetricsOptions("currentYear"), shift = 0)
```

## Arguments

- year:

  an integer value or integer vector for the year(s).

- shift:

  an integer value, the number of days shifted from the Easter date.
  Negative integers are allowed.

## Details

Holidays may have two origins, ecclesiastical and public/federal. The
ecclesiastical calendars of Christian churches are based on cycles of
moveable and immoveable feasts. Christmas, December 25th, is the
principal immoveable feast. Easter is the principal moveable feast, and
dates of most other moveable feasts are determined with respect to
Easter.

The date of Easter is evaluated by a complex procedure whose detailed
explanation goes beyond this description. The reason that the
calculation is so complicate is, because the date of Easter is linked to
(an inaccurate version of) the Hebrew calendar. But nevertheless a short
answer to the question "When is Easter?" is the following: Easter Sunday
is the first Sunday after the first full moon after vernal equinox. For
the long answer we refer to Toendering (1998).

The algorithm computes the date of Easter based on the algorithm of
Oudin (1940). It is valid for any Gregorian Calendar year.

## Value

the date of Easter as an object of class `"timeDate"`

## Note

Doesn't have options to compute Eastern Orthodox Easter dates.

## See also

[`BoxingDay`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md),
etc., for descriptions of the individual holiday functions,

[`listHolidays`](https://geobosh.github.io/timeDateDoc/reference/holiday-Listing.md)
for a list (character vector) of all holidays,

[`holiday`](https://geobosh.github.io/timeDateDoc/reference/holiday.md)
alternative to calling directly individual holiday functions (takes one
or more holiday functions as argument),

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
[`holidayZURICH`](https://geobosh.github.io/timeDateDoc/reference/holiday-ZURICH.md)
for holidays at major financial centers.

## Examples

``` r
## Easter
# current year
Easter()
#> GMT
#> [1] [2025-04-20]
   
## From 2001 to 2010:
Easter(2001:2010)
#> GMT
#>  [1] [2001-04-15] [2002-03-31] [2003-04-20] [2004-04-11] [2005-03-27]
#>  [6] [2006-04-16] [2007-04-08] [2008-03-23] [2009-04-12] [2010-04-04]
```
