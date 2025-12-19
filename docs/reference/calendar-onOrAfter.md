# On-or-after/before dates

Compute the date that is a "on-or-after" or "on-or-before" n-day.

## Usage

``` r
timeNdayOnOrAfter(charvec, nday = 1, format = "%Y-%m-%d", 
    zone = "", FinCenter = "")
    
timeNdayOnOrBefore(charvec, nday = 1, format = "%Y-%m-%d", 
    zone = "", FinCenter = "")
```

## Arguments

- charvec:

  a character vector or object from a class representing time, such as
  `"timeDate"`, `"POSIXlt"`, etc.

- nday:

  an integer vector with entries ranging from `0` (Sunday) to `6`
  (Saturday).

- format:

  the format specification of the input character vector.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  "continent/city".

## Details

`timeNdayOnOrAfter` returns the date in the specified month that is a
n-day (e.g. Sunday) on or after the given date. Month and date are given
through argument `charvec`.

The function `timeNdayOnOrBefore` returns the date that is a n-day on or
before the given date.

## Value

an object of class `"timeDate"`

## See also

[`trunc.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),

[`timeFirstDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeFirstDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),

[`timeNthNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),
[`timeLastNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),

## Examples

``` r
## date as character string
charvec = "2006-04-16"
   
## timeNdayOnOrAfter
# What date has the first Monday on or after March 15, 1986?
timeNdayOnOrAfter("1986-03-15", 1)
#> GMT
#> [1] [1986-03-17]
    
## timeNdayOnOrBefore
# What date has Friday on or before April 22, 1977?
timeNdayOnOrBefore("1986-03-15", 5)
#> GMT
#> [1] [1986-03-14]
```
