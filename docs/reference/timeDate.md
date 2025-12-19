# Create 'timeDate' objects

Create a `"timeDate"` object from scratch from a character vector or
other suitable objects.

## Usage

``` r
timeDate(charvec, format = NULL, zone = "", FinCenter = "", ...)

# S4 method for class 'character'
timeDate(charvec, format = NULL, zone = "", FinCenter = "", 
         dst_gap = "+")

## methods for as.timeDate
# Default S3 method
as.timeDate(x, zone = "", FinCenter = "")  

# S3 method for class 'POSIXt'
as.timeDate(x, zone = "", FinCenter = "")

# S3 method for class 'Date'
as.timeDate(x, zone = "", FinCenter = "")

# S3 method for class 'timeDate'
as.timeDate(x, zone = x@FinCenter, FinCenter = "")  

strptimeDate(x, format = whichFormat(x), tz = "")
```

## Arguments

- charvec:

  a character vector or vector of dates and times.

- format:

  the format specification of the input character vector.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  "continent/city".

- dst_gap:

  a character string specifying what to do with non-existent times
  falling in a DST gap: add an hour (`"+"`), subtract an hour (`"-"`),
  set to `NA` (`"NA"`), or ignore (`""`). When the ‘ignore’ option is
  used the code to check for this kind of faulty times is skipped and
  the result will be equivalent to `"+"` or `"-"` but which one is not
  defined. This could be useful when you are certain that there are no
  times in DST gaps or don't care how they are dealt with.

- x:

  for `strptimeDate`, a character string or vector of dates and times.
  For the `as.timeDate` methods, an object from a class that can be
  converted to `"timeDate"`. The default method converts `x` to
  `character`.

- tz:

  a character with the location of the financial center named as
  `"continent/city"`, or short `"city"`.

- ...:

  further arguments for methods.

## Details

`timeDate` creates objects from class `"timeDate"` from character
vectors, objects from several date/time classes, and other suitable
objects.. It is an S4 generic function and this page describes the
methods defined in package timeDate, see section ‘Methods’.

Note that `zone` is the time zone of the input, while `FinCenter` is the
‘current’ time zone, typically but not necessarilly where the code is
run. To change one or both of these time zones of an existing
`"timeDate"` object, call `timeDate()` on it, see the method for
`charvec = "timeDate"` in section ‘Methods’.

The methods for `as.timeDate` call `timeDate`, maybe after some minor
preparation. The default method for `as.timeDate` converts `x` to
`character` before calling `timeDate`.

`strptimeDate` is a wrapper of `timeDate`, suitable when `zone` and
`FinCenter` are the same, It has the same arguments as
[`strptime`](https://rdrr.io/r/base/strptime.html). If `format` is
missing it tries to deduce it. If `tz` is missing it sets it to the
value of the Rmetrics option `"myFinCenter"`.

## Value

an object of class `"timeDate"`

## Methods

The following methods for `timeDate` are defined in package timeDate.

- `signature(charvec = "ANY")`:

  Converts `charvec` to `character` and calls `timeDate` on the result.

- `signature(charvec = "character")`:

  ...

- `signature(charvec = "Date")`:

  ...

- `signature(charvec = "missing")`:

  Returns the current time as `"timeDate"` object.

- `signature(charvec = "numeric")`:

  ...

- `signature(charvec = "POSIXt")`:

  ...

- `signature(charvec = "timeDate")`:

  Changes the time zone and/or financial center of `charvec` to the
  requested ones. If `zone` is missing or equal to the empty string,
  just changes the financial center.

## See also

[`as.character`](https://geobosh.github.io/timeDateDoc/reference/methods-as.md),
[`as.POSIXct`](https://geobosh.github.io/timeDateDoc/reference/methods-as.md),
etc., for conversion from `"timeDate"` to other classes

## Examples

``` r
## character vector strings:
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55",   "10:34:02",   "08:30:00",   "11:18:23")

dts; tms
#> [1] "1989-09-28" "2001-01-15" "2004-08-30" "1990-02-09"
#> [1] "23:12:55" "10:34:02" "08:30:00" "11:18:23"

t1 <- timeDate(dts, format = "%Y-%m-%d", FinCenter = "GMT" )
t1
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]

stopifnot(identical(t1, timeDate(dts, FinC = "GMT"))) # auto-format

timeDate(dts, format = "%Y-%m-%d", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [2004-08-30 02:00:00]
#> [4] [1990-02-09 01:00:00]

timeDate(paste(dts, tms), format = "%Y-%m-%d %H:%M:%S",
     zone = "GMT", FinCenter = "GMT")
#> GMT
#> [1] [1989-09-28 23:12:55] [2001-01-15 10:34:02] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:23]

timeDate(paste(dts, tms), 
     zone = "Europe/Zurich", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-28 23:12:55] [2001-01-15 10:34:02] [2004-08-30 08:30:00]
#> [4] [1990-02-09 11:18:23]

timeDate(paste(dts, tms), format = "%Y-%m-%d %H:%M:%S",
     zone = "GMT", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-29 00:12:55] [2001-01-15 11:34:02] [2004-08-30 10:30:00]
#> [4] [1990-02-09 12:18:23]

## non standard format:
timeDate(paste(20:31, "03.2005", sep="."), format = "%d.%m.%Y")
#> GMT
#>  [1] [2005-03-20] [2005-03-21] [2005-03-22] [2005-03-23] [2005-03-24]
#>  [6] [2005-03-25] [2005-03-26] [2005-03-27] [2005-03-28] [2005-03-29]
#> [11] [2005-03-30] [2005-03-31]

## ISO and American formats are auto-detected:
timeDate("2004-12-31", FinCenter = "GMT")
#> GMT
#> [1] [2004-12-31]
timeDate("12/11/2004", FinCenter = "GMT")
#> GMT
#> [1] [2004-12-11]
timeDate("1/31/2004") # auto-detect American format
#> GMT
#> [1] [2004-01-31]

## ... from POSIX?t, and containing NAs:
lsec <- as.POSIXlt(.leap.seconds)
lsec
#>  [1] "1972-07-01 GMT" "1973-01-01 GMT" "1974-01-01 GMT" "1975-01-01 GMT"
#>  [5] "1976-01-01 GMT" "1977-01-01 GMT" "1978-01-01 GMT" "1979-01-01 GMT"
#>  [9] "1980-01-01 GMT" "1981-07-01 GMT" "1982-07-01 GMT" "1983-07-01 GMT"
#> [13] "1985-07-01 GMT" "1988-01-01 GMT" "1990-01-01 GMT" "1991-01-01 GMT"
#> [17] "1992-07-01 GMT" "1993-07-01 GMT" "1994-07-01 GMT" "1996-01-01 GMT"
#> [21] "1997-07-01 GMT" "1999-01-01 GMT" "2006-01-01 GMT" "2009-01-01 GMT"
#> [25] "2012-07-01 GMT" "2015-07-01 GMT" "2017-01-01 GMT"
lsec[c(2,4:6)] <- NA
timeDate(lsec)
#> GMT
#>  [1] [1972-07-01] [NA]         [1974-01-01] [NA]         [NA]        
#>  [6] [NA]         [1978-01-01] [1979-01-01] [1980-01-01] [1981-07-01]
#> [11] [1982-07-01] [1983-07-01] [1985-07-01] [1988-01-01] [1990-01-01]
#> [16] [1991-01-01] [1992-07-01] [1993-07-01] [1994-07-01] [1996-01-01]
#> [21] [1997-07-01] [1999-01-01] [2006-01-01] [2009-01-01] [2012-07-01]
#> [26] [2015-07-01] [2017-01-01]

dtms <- paste(dts,tms)
dtms[2:3] <- NA
timeDate(dtms, FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-29 00:12:55] [NA]                  [NA]                 
#> [4] [1990-02-09 12:18:23]

## NAs in dates and/or times
dts2 <- c("1989-09-28", NA, "2004-08-30", "1990-02-09")
tms2 <- c(  "23:12:55",   "10:34:02",   NA,   "11:18:23")
## this throws error (since NAs are converted to the string "NA"):
## timeDate(paste(dts,tms), FinCenter = "Europe/Zurich")
## ## Error in midnightStandard2(charvec, format) :
## ##   'charvec' has non-NA entries of different number of characters
##
## these work:
td1 <- timeDate(pasteMat(cbind(dts, tms)), FinCenter = "Europe/Zurich")
td2 <- timeDate(pasteMat(dts, tms), FinCenter = "Europe/Zurich")
identical(td1, td2) ## TRUE
#> [1] TRUE

## NA's that appear due to non-existent times;
## on 27/03/1983 in Sofia the clock jumped at midnight to 1am
Sofia_to_DST_char <- c("1983-03-26 23:00:00",
    "1983-03-27 00:00:00", # change to DST; 0am doesn't exist in Sofia on this date
    "1983-03-27 01:00:00",
    "1983-03-27 02:00:00",
    "1983-03-27 03:00:00")

## by default, the non-existent time is moved to the next valid time,
## this is equivalent to dst_gap = "+"
Sofia_to_DST <- timeDate(Sofia_to_DST_char, zone = "Sofia", FinCenter = "Sofia")

## use dst_gap = "NA" to turn invalid times into NA's
Sofia_to_DSTa <- timeDate(Sofia_to_DST_char, zone = "Sofia", FinCenter = "Sofia",
                          dst_gap = "NA")
Sofia_to_DSTa
#> Sofia
#> [1] [1983-03-26 23:00:00] [NA]                  [1983-03-27 01:00:00]
#> [4] [1983-03-27 02:00:00] [1983-03-27 03:00:00]

cbind(Sofia_to_DST_char,
      Sofia_to_DST = format(Sofia_to_DST),
      Sofia_to_DSTa = format(Sofia_to_DSTa)
      )
#>      Sofia_to_DST_char     Sofia_to_DST          Sofia_to_DSTa        
#> [1,] "1983-03-26 23:00:00" "1983-03-26 23:00:00" "1983-03-26 23:00:00"
#> [2,] "1983-03-27 00:00:00" "1983-03-27 01:00:00" NA                   
#> [3,] "1983-03-27 01:00:00" "1983-03-27 01:00:00" "1983-03-27 01:00:00"
#> [4,] "1983-03-27 02:00:00" "1983-03-27 02:00:00" "1983-03-27 02:00:00"
#> [5,] "1983-03-27 03:00:00" "1983-03-27 03:00:00" "1983-03-27 03:00:00"

## dst_gap = "-" rolls the invalid time back
Sofia_to_DSTb <- timeDate(Sofia_to_DST_char, zone = "Sofia", FinCenter = "Sofia",
                          dst_gap = "-")
Sofia_to_DSTb
#> Sofia
#> [1] [1983-03-26 23:00:00] [1983-03-26 23:00:00] [1983-03-27 01:00:00]
#> [4] [1983-03-27 02:00:00] [1983-03-27 03:00:00]

## Coerce a 'Date' object into a 'timeDate' object:
as.timeDate(Sys.Date())
#> GMT
#> [1] [2025-12-19]
```
