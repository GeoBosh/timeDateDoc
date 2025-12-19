# Ceiling (round up) for data-time objects

Round up a data-time object to the next time unit (day, mhour, month,
etc.).

## Usage

``` r
timeCeiling(x, ...)

# S3 method for class 'POSIXt'
timeCeiling(x, 
    units = c("days", "hours", "mins", "secs", "months", "years"),
    ...)

# S3 method for class 'timeDate'
timeCeiling(x, 
    units = c("days", "hours", "mins", "secs", "months", "years"), 
    ...)
```

## Arguments

- x:

  an object representing date-time.

- units:

  a character string, one of the supported units of time.

- ...:

  further arguments for methods.

## Details

`timeCeiling` rounds up to the start of the next time unit, as specified
by argument `units`.

## Value

for the `"timeDate"` method, a `"timeDate"` object,

for the `"POSIXt"` method, a `"POSIXlt"` object

## Author

Georgi N. Boshnakov

## Note

[`base::ceiling`](https://rdrr.io/r/base/Round.html) is generic but time
methods cannot be defined for it since it has only one argument. The
same holds for its relative
[`base::floor`](https://rdrr.io/r/base/Round.html).

On the other hand, [`base::trunc`](https://rdrr.io/r/base/Round.html)
and [`base::round`](https://rdrr.io/r/base/Round.html) accept further
arguments and therefore `"timeDate"` methods are defined for them. In
fact the method for `trunc` plays the role of `floor`.

## See also

[`trunc.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),
[`trunc.POSIXt`](https://rdrr.io/r/base/round.POSIXt.html),

[`round.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),
[`round.POSIXt`](https://rdrr.io/r/base/round.POSIXt.html),

## Examples

``` r
# create a timeDate object
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55.13",   "10:34:02.23",   "08:30:00.33",   "11:18:23.53")
td <- timeDate(paste(dts, tms), format = "%Y-%m-%d %H:%M:%S",
               zone = "GMT", FinCenter = "GMT")

## timeCeiling
timeCeiling(td) # same as timeCeiling(td, "days")
#> GMT
#> [1] [1989-09-29] [2001-01-16] [2004-08-31] [1990-02-10]

timeCeiling(td, "secs")
#> GMT
#> [1] [1989-09-28 23:12:55] [2001-01-15 10:34:02] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:23]
timeCeiling(td, "mins")
#> GMT
#> [1] [1989-09-28 23:13:00] [2001-01-15 10:35:00] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:19:00]
timeCeiling(td, "hours")
#> GMT
#> [1] [1989-09-29 00:00:00] [2001-01-15 11:00:00] [2004-08-30 09:00:00]
#> [4] [1990-02-09 12:00:00]
timeCeiling(td, "days")
#> GMT
#> [1] [1989-09-29] [2001-01-16] [2004-08-31] [1990-02-10]
timeCeiling(td, "months")
#> GMT
#> [1] [1989-10-01] [2001-02-01] [2004-09-01] [1990-03-01]
timeCeiling(td, "years")
#> GMT
#> [1] [1990-01-01] [2002-01-01] [2005-01-01] [1991-01-01]

## rounding with "days" usually sets the time to midnight (the start of a day),
## but it may not exist
Sofia_to_DST_char <- c("1983-03-26 23:00:00",
    "1983-03-27 00:00:00", # change to DST; 0am doesn't exist in Sofia on this date
    "1983-03-27 01:00:00",
    "1983-03-27 02:00:00",
    "1983-03-27 03:00:00")

Sofia_to_DST <- timeDate(Sofia_to_DST_char, zone = "Sofia", FinCenter = "Sofia")
cbind(Sofia_to_DST_char, format(Sofia_to_DST@Data))
#>      Sofia_to_DST_char                          
#> [1,] "1983-03-26 23:00:00" "1983-03-26 21:00:00"
#> [2,] "1983-03-27 00:00:00" "1983-03-26 22:00:00"
#> [3,] "1983-03-27 01:00:00" "1983-03-26 22:00:00"
#> [4,] "1983-03-27 02:00:00" "1983-03-26 23:00:00"
#> [5,] "1983-03-27 03:00:00" "1983-03-27 00:00:00"

## on 27/03/1983 in Sofia the clock jumped at midnight to 1am, so the
## day started at 1am - hence the first time below.  the rest are on the
## next day, which starts at midnight.
timeCeiling(Sofia_to_DST) # same as timeCeiling(Sofia_to_DST, "days")
#> Sofia
#> [1] [1983-03-27 01:00:00] [1983-03-28 00:00:00] [1983-03-28 00:00:00]
#> [4] [1983-03-28 00:00:00] [1983-03-28 00:00:00]

trunc(Sofia_to_DST)
#> Sofia
#> [1] [1983-03-26 00:00:00] [1983-03-27 01:00:00] [1983-03-27 01:00:00]
#> [4] [1983-03-27 01:00:00] [1983-03-27 01:00:00]

## to avoid confusion, set non-existent times to NA
Sofia_to_DSTa <- timeDate(Sofia_to_DST_char, zone = "Sofia", FinCenter = "Sofia",
                          dst_gap = "NA")
Sofia_to_DSTa
#> Sofia
#> [1] [1983-03-26 23:00:00] [NA]                  [1983-03-27 01:00:00]
#> [4] [1983-03-27 02:00:00] [1983-03-27 03:00:00]
timeCeiling(Sofia_to_DSTa)
#> Sofia
#> [1] [1983-03-27 01:00:00] [NA]                  [1983-03-28 00:00:00]
#> [4] [1983-03-28 00:00:00] [1983-03-28 00:00:00]
```
