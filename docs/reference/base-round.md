# Rounding and truncating 'timeDate' objects

Rounds and truncates objects of class 'timeDate'.

## Usage

``` r
# S3 method for class 'timeDate'
round(x, digits = c("days", "hours", "mins", "secs", "months", "years"))

# S3 method for class 'timeDate'
trunc(x, units = c("days", "hours", "mins", "secs", "months", "years"),
    ...)
```

## Arguments

- digits, units:

  a character string denoting the date/time units in which the results
  are desired.

- x:

  an object of class `"timeDate"`.

- ...:

  arguments passed to other methods.

## Details

The two functions `round` and `trunc` allow to round or to truncate
`"timeDate"` objects to the specified unit and return them as
`"timeDate"` objects.

There is an inconsistency in that `round` uses `digits` as argument and
not `units`.

From ‘timeDate’ version \\\>\\ 4041.110, the units of rounding are the
same as those for `round.POSIXt` and `trunc.POSIXt`. Note though that
the default for the ‘timeDate’ methods is `"days"`, not `"secs"`.

## Value

an object of class `"timeDate"`

## See also

[`timeFirstDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeFirstDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),

[`timeNthNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),
[`timeLastNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),

[`timeNdayOnOrAfter`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md),
[`timeNdayOnOrBefore`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md)

## Examples

``` r
# create a timeDate object
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55.13",   "10:34:02.23",   "08:30:00.33",   "11:18:23.53")
td <- timeDate(paste(dts, tms), format = "%Y-%m-%d %H:%M:%S",
               zone = "GMT", FinCenter = "GMT")

## round
round(td) # same as round(td, "days")
#> GMT
#> [1] [1989-09-29] [2001-01-15] [2004-08-30] [1990-02-09]

round(td, "secs")
#> GMT
#> [1] [1989-09-28 23:12:55] [2001-01-15 10:34:02] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:23]
round(td, "mins")
#> GMT
#> [1] [1989-09-28 23:13:00] [2001-01-15 10:34:00] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:00]
round(td, "hours")
#> GMT
#> [1] [1989-09-28 23:00:00] [2001-01-15 11:00:00] [2004-08-30 09:00:00]
#> [4] [1990-02-09 11:00:00]
round(td, "days")
#> GMT
#> [1] [1989-09-29] [2001-01-15] [2004-08-30] [1990-02-09]
round(td, "months")
#> GMT
#> [1] [1989-10-01] [2001-01-01] [2004-09-01] [1990-02-01]
round(td, "years")
#> GMT
#> [1] [1990-01-01] [2001-01-01] [2005-01-01] [1990-01-01]


## truncate
trunc(td) # same as trunc(td, "days")
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]

trunc(td, "secs")
#> GMT
#> [1] [1989-09-28 23:12:55] [2001-01-15 10:34:02] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:23]
trunc(td, "mins")
#> GMT
#> [1] [1989-09-28 23:12:00] [2001-01-15 10:34:00] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:00]
trunc(td, "hours")
#> GMT
#> [1] [1989-09-28 23:00:00] [2001-01-15 10:00:00] [2004-08-30 08:00:00]
#> [4] [1990-02-09 11:00:00]
trunc(td, "days")
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]
trunc(td, "months")
#> GMT
#> [1] [1989-09-01] [2001-01-01] [2004-08-01] [1990-02-01]
trunc(td, "years")
#> GMT
#> [1] [1989-01-01] [2001-01-01] [2004-01-01] [1990-01-01]
```
