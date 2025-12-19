# Regularly spaced 'timeDate' objects

Create a regularly spaced object of class `"timeDate"`.

## Usage

``` r
timeSequence(from, to = Sys.timeDate(), by, length.out = NULL,
            format = NULL, zone = "", FinCenter = "")

# S3 method for class 'timeDate'
seq(from, to, by, length.out = NULL, along.with = NULL, ...)
```

## Arguments

- from, to:

  starting date, required, and end date, optional. If supplied, `to`
  must be after (later than) `from`.

- by:

  - a character string, containing one of "sec", "min", "hour", "day",
    "week", "month" or "year". This can optionally be preceded by an
    integer and a space, or followed by "s".

  - character string "quarter" that is equivalent to "3 months".

  - a number, taken to be in seconds.

  - an object of class 'difftime'.

  - character string `"DSTday"` gives a sequence taken at the same clock
    time every day. Note that on the days when the DST changes, the
    requested time may not exist or be ambiguous, see the examples.

- length.out:

  integer, optional. Desired length of the sequence, if specified "to"
  will be ignored.

- along.with:

  Take the length from the length of this argument.

- format:

  the format specification of the input character vector.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  "continent/city".

- ...:

  arguments passed to other methods.

## Note

`timeSequence()` is a wrapper for the `"timeDate"` method of `seq()`,
and that has been closely modeled after base R's `POSIXt` method,
[`seq.POSIXt`](https://rdrr.io/r/base/seq.POSIXt.html).

## Value

an object of class
`"`[`timeDate`](https://geobosh.github.io/timeDateDoc/reference/class-timeDate.md)`"`

## Examples

``` r
## timeSequence

## autodetection of format
(t1 <- timeSequence(from = "2004-03-12", to = "2004-04-11"))
#> GMT
#>  [1] [2004-03-12] [2004-03-13] [2004-03-14] [2004-03-15] [2004-03-16]
#>  [6] [2004-03-17] [2004-03-18] [2004-03-19] [2004-03-20] [2004-03-21]
#> [11] [2004-03-22] [2004-03-23] [2004-03-24] [2004-03-25] [2004-03-26]
#> [16] [2004-03-27] [2004-03-28] [2004-03-29] [2004-03-30] [2004-03-31]
#> [21] [2004-04-01] [2004-04-02] [2004-04-03] [2004-04-04] [2004-04-05]
#> [26] [2004-04-06] [2004-04-07] [2004-04-08] [2004-04-09] [2004-04-10]
#> [31] [2004-04-11]

stopifnot( ## different formats even:
  identical(t1, timeSequence(from = "2004-03-12", to = "11-Apr-2004")),
  identical(t1, ## explicit format and FinCenter :
      timeSequence(from = "2004-03-12", to = "2004-04-11",
                   format = "%Y-%m-%d", FinCenter = "GMT")))

## observe "switch to summer time":
timeSequence(from = "2004-03-26 05:00:00", to = "2004-04-02 05:00:00",
             zone = "Europe/Zurich", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [2004-03-26 05:00:00] [2004-03-27 05:00:00] [2004-03-28 06:00:00]
#> [4] [2004-03-29 06:00:00] [2004-03-30 06:00:00] [2004-03-31 06:00:00]
#> [7] [2004-04-01 06:00:00]

## ensure fixed clock time:
timeSequence(from = "2004-03-26 05:00:00", to = "2004-04-01 05:00:00",
             by = "DSTday", zone = "Europe/Zurich", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [2004-03-26 05:00:00] [2004-03-27 05:00:00] [2004-03-28 05:00:00]
#> [4] [2004-03-29 05:00:00] [2004-03-30 05:00:00] [2004-03-31 05:00:00]
#> [7] [2004-04-01 05:00:00]

## on the day of DST change the time may not exist (notice 2004-03-28 00:00:00):
timeSequence(from = "2004-03-26 01:00:00", to = "2004-04-01 01:00:00",
             by = "DSTday", zone = "Europe/Zurich", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [2004-03-26 01:00:00] [2004-03-27 01:00:00] [2004-03-28 02:00:00]
#> [4] [2004-03-29 01:00:00] [2004-03-30 01:00:00] [2004-03-31 01:00:00]
#> [7] [2004-04-01 01:00:00]
```
