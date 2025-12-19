# Class "timeDate"

Class `"timeDate"` represents date and time objects.

## Objects from the Class

Objects can be created by calls of the functions
[`timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md),
[`timeSequence`](https://geobosh.github.io/timeDateDoc/reference/timeDate-Sequence.md),
[`timeCalendar`](https://geobosh.github.io/timeDateDoc/reference/timeDate-Calendar.md)
and
[`as.timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md),
among others. There is also a `"timeDate"` method for
[`seq`](https://geobosh.github.io/timeDateDoc/reference/timeDate-Sequence.md).

## Slots

- `Data`::

  Object of class `"POSIXct"`: a vector of POSIXct dates and times
  always related to "GMT".

- `format`::

  Object of class `"character"`: a character string denoting the format
  specification of the input data character vector.

- `FinCenter`::

  Object of class `"character"`: a character string with the location of
  the financial center named as "continent/city", or just "city".

## Details

For the management of chronological objects under R three concepts are
available: The first is the implementation of date and time in R's
`chron` package neglecting locals, time zones and day light saving
times. This approach is in most cases appropriate for economic time
series. The second approach, available in R's base package implements
the POSIX standard to date and time objects, named `"POSIXt"`.

Unfortunately, the representation of these objects is in some cases
operating system dependent and especially under MS Windows several
problems appeared over the time in the management of time zones and day
light saving times. Rmetrics overcomes these difficulties with POSIX
objects and introduce a new S4 class of `"timeDate"` objects which allow
for powerful methods to represent dates and times in different financial
centers around the world.

Many of the basic functionalities of these objects are in common with
S-Plus' `"timeDate"` objects and thus many of your privately written
functions for SPlus/FinMetrics may also be used within the R/Rmetrics
environment.

A major difference is the time zone concept which is replaced by the
"Financial Center" concept. The `FinCenter` character variable specifies
where you are living and at which financial center you are working. With
the variable `myFinCenter` you can overwrite the default setting with
your personal settings. With the specification of the `FinCenter` your
system knows what rules rules for day light saving times should be
applied, what is your holiday calendar, what is your currency, what are
your interest rate conventions. (Not all specifications are already
implemented.) Many other aspects can be easily accessed when a financial
center is named. So we can distinguish between Frankfurt and Zurich,
which both belong to the same time zone, but differed in DST changes in
the eighties and have different holiday calendars. Futhermore, since the
underlying time refers to "GMT" and DST rules and all other information
is available in local (ASCII) databases, we are sure, that R/Rmetrics
delivers with such a date/time concept on every computer independent of
the operating systemin use, identical results.

Another important feature of the `"timeDate"` concept used here is the
fact that we don't rely on American or European ways to write dates. We
use consequently the ISO-8601 standard for date and time notations.  

**Generation of `"timeDate"` Objects**

We have defined a `"timeDate"` class which is in many aspects similar to
the S-Plus class with the same name, but has also some important
advantageous differeneces. The S4 class has four Slots, the `Data` slot
which holds date and time as 'POSIXct' objects in the standard ISO-8601
format, the `Dim` slot which gives the dimension of the data object
(i.e. its length), the `format` specification slot and the `FinCenter`
slot which holds the name of the financial center. By default this is
the value

Three functions allow to cgenerate date/time objects: `"timeDate"` from
character vectors, `timeCalendar` from date and time atoms, and
`timeSequence` from a "from/to" or from a "from/length" sequence
specification. Note, time zone transformations are easily handled by by
the `"timeDate"` functions which can also take `"timeDate"` and `POSIXt`
objects as inputs, while transforming them between financial centers
and/or time zones specified by the arguments `zone` and `FinCenter`.
Finally the function `Sys.timeDate` returns current system time in form
of a `"timeDate"` object.  

**Tests and Representation of timeDate Objects:**

Rmetrics has implemented several methods to represent `"timeDate"`
objects. For example, the print method returns the date/time in square
`"[]"` brackets to distinguish the output from other date and time
objects. On top of the date and time output the name of the `FinCenter`
is printed. The summary method returns a printed report with information
about the `"timeDate"` object. Finally, the format methods allows to
transform objects into a ISO conform formatted character strings.  

**Mathematical Operations:**

Rmetrics supports methods to perform many mathematical operations.
Included are methods to extract or to replace subsets from `"timeDate"`
objects, to perform arithmetic `"+"` and `"-"` operations, to group
[`Ops`](https://rdrr.io/r/base/groupGeneric.html) generic functions, to
return suitably lagged and iterated differences
[`diff`](https://geobosh.github.io/timeDateDoc/reference/base-diff.md),
to return differences
[`difftimeDate`](https://geobosh.github.io/timeDateDoc/reference/base-difftimeDate.md)
of two `"timeDate"` objects, to concatenate objects, to replicate
objects, to
[`round`](https://geobosh.github.io/timeDateDoc/reference/base-round.md)
objects, to truncate objects using
[`trunc`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),
to extract the first or last entry of a vector, to
[`sort`](https://geobosh.github.io/timeDateDoc/reference/base-sort.md)
the objects of the elements of a date/time vector, and to revert
`"timeDate"` vector objects, among other functions.  

**Transformation of Objects:**

Rmetrics has also functions to transform dat/time objects between
different representations. Included are methods to transform
`"timeDate"` objects to character strings, to data frames, to POSIXct or
POSIXlt objects, to
[`julian`](https://geobosh.github.io/timeDateDoc/reference/calendar-julian.md)
counts. One can extract date/time `atoms` from calendar dates, and the
[`months`](https://geobosh.github.io/timeDateDoc/reference/calendar-julian.md)
atoms from a `"timeDate"` object.

## Note

Originally, these functions were written for Rmetrics users using R and
Rmetrics under Microsoft's Windows XP operating system where time zones,
daylight saving times and holiday calendars are not or insufficiently
supported.

The usage of the Ical Library and the introduction of the FinCenter
concept was originally develloped for R Version 1.5. The `"timeDate"`
and `timeSeries` objects were added for R Version 1.8.1. Minor changes
were made to adapt the functions for R Version 1.9.1. As a consequence,
newer concepts like the `Date` objects were not yet considered and
included in this collection of date and time concepts. With R Version
2.3.0 a major update has been made adding many new generic functions and
renaming a few already existing functions, please be aware of this.

Note, the date/time conversion from an arbitrary time zone to GMT cannot
be unique, since date/time objects appear twice during the hour when DST
changes and the isdt flag was not recorded. A bookkeeping which takes
care if DST is effective or not is not yet included. However, in most
applications this is not necessary since the markets are closed on
weekends, especially at times when DST usually changes. It is planned
for the future to implement the DST supporting this facility.

The ISO-8601 midnight standard has been implemented. Note, that for
example "2005-01-01 24:00:00" is accepted as a valid date/time string.

Also available is an automated format recognition, so the user does not
have to specify the format string for the most common date/time formats.

## Methods

- timeDate:

  `signature(charvec = "timeDate")`: create objects from class
  `"timeDate"`, see
  [`timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md);

- show:

  `signature(object = "timeDate")`: prints an object of class
  `"timeDate"`;

- plot:

  `signature(x = "timeDate")`:

- points:

  `signature(x = "timeDate")`:

- lines:

  `signature(x = "timeDate")`:

- abline:

  `signature(a = "ANY", b = "ANY", h = "ANY", v = "timeDate")`: see
  `plot-methods`.

- \$:

  `signature(x = "timeDate")`: ...

- \[:

  `signature(x = "timeDate", i = "ANY", j = "missing")`:

- \[:

  `signature(x = "timeDate", i = "character", j = "missing")`:

- \[:

  `signature(x = "timeDate", i = "logical", j = "missing")`:

- \[:

  `signature(x = "timeDate", i = "missing", j = "missing")`:

- \[:

  `signature(x = "timeDate", i = "numeric", j = "missing")`: take parts
  of a `"timeDate"` object, see
  [`subset`](https://geobosh.github.io/timeDateDoc/reference/base-subset.md).

- finCenter:

  `signature(x = "timeDate")`:

- finCenter\<-:

  `signature(x = "timeDate")`: see
  [`finCenter`](https://geobosh.github.io/timeDateDoc/reference/timeDate-finCenter.md).

- atoms:

  `signature(x = "timeDate")`:

- align:

  `signature(x = "timeDate")`: see
  [`align`](https://geobosh.github.io/timeDateDoc/reference/calendar-align.md).

- isDaily:

  `signature(x = "timeDate")`:

- isMonthly:

  `signature(x = "timeDate")`:

- isQuarterly:

  `signature(x = "timeDate")`:

- isRegular:

  `signature(x = "timeDate")`: see see
  [`isRegular`](https://geobosh.github.io/timeDateDoc/reference/calendar-isRegular.md).

- frequency:

  `signature(x = "timeDate")`: see
  [`frequency`](https://geobosh.github.io/timeDateDoc/reference/calendar-isRegular.md).

- is.na:

  `signature(x = "timeDate")`: see
  [`is.na-methods`](https://geobosh.github.io/timeDateDoc/reference/stats-na-fail.md).

- sample:

  `signature(x = "timeDate")`: see
  [`sample`](https://geobosh.github.io/timeDateDoc/reference/base-sample.md).

- Ops:

  `signature(e1 = "timeDate", e2 = "timeDate")`:

- +:

  `signature(e1 = "numeric", e2 = "timeDate")`:

- +:

  `signature(e1 = "timeDate", e2 = "numeric")`:

- +:

  `signature(e1 = "timeDate", e2 = "timeDate")`:

- -:

  `signature(e1 = "numeric", e2 = "timeDate")`:

- -:

  `signature(e1 = "timeDate", e2 = "numeric")`:

- -:

  `signature(e1 = "timeDate", e2 = "timeDate")`: see
  [`timeDateMathOps`](https://geobosh.github.io/timeDateDoc/reference/methods-mathOps.md).

- coerce:

  `signature(from = "ANY", to = "timeDate")`:

- coerce:

  `signature(from = "Date", to = "timeDate")`:

- coerce:

  `signature(from = "POSIXt", to = "timeDate")`:

- coerce:

  `signature(from = "timeDate", to = "character")`:

- coerce:

  `signature(from = "timeDate", to = "data.frame")`:

- coerce:

  `signature(from = "timeDate", to = "Date")`:

- coerce:

  `signature(from = "timeDate", to = "list")`:

- coerce:

  `signature(from = "timeDate", to = "numeric")`:

- coerce:

  `signature(from = "timeDate", to = "POSIXct")`:

- coerce:

  `signature(from = "timeDate", to = "POSIXlt")`: convert from/to
  `"timeDate"` objects. These are methods for `as`, to be used with the
  syntax `as(from, to)`, where `from` is the object to be converted and
  `to` is the desired target class. Most conversions can also be done
  with specialised functions such as `as.character` and `as.timeDate`,
  see
  [`as.timeDate`](https://geobosh.github.io/timeDateDoc/reference/timeDate.md).

- names:

  `signature(x = "timeDate")`:

- names\<-:

  `signature(x = "timeDate")`: see
  [`names-methods`](https://geobosh.github.io/timeDateDoc/reference/methods-names.md).

- getDataPart:

  `signature(object = "timeDate")`: ...

- initialize:

  `signature(.Object = "timeDate")`: ...

## Examples

``` r
## Examples for Objects of class 'timeDate'

## Sys.timeDate()           # direct
## timeDate(Sys.time())     # transformed from "POSIX(c)t"

## local time in Zurich
## timeDate(Sys.time(), FinCenter = "Zurich")  

## character vector strings for the examples below
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55",   "10:34:02",   "08:30:00",   "11:18:23")

t1 <- timeDate(dts, format = "%Y-%m-%d", FinCenter = "GMT" )
t1a <- timeDate(dts, FinCenter = "GMT")  # auto-format
identical(t1, t1a)
#> [1] TRUE

t1
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]

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

## non standard format
timeDate(paste(20:31, "03.2005", sep="."), format = "%d.%m.%Y")
#> GMT
#>  [1] [2005-03-20] [2005-03-21] [2005-03-22] [2005-03-23] [2005-03-24]
#>  [6] [2005-03-25] [2005-03-26] [2005-03-27] [2005-03-28] [2005-03-29]
#> [11] [2005-03-30] [2005-03-31]

## Note, ISO and American formats are auto-detected
timeDate("2004-12-31", FinCenter = "GMT")
#> GMT
#> [1] [2004-12-31]
timeDate("12/11/2004", FinCenter = "GMT")
#> GMT
#> [1] [2004-12-11]
timeDate("1/31/2004") # auto-detect American format
#> GMT
#> [1] [2004-01-31]

## ... from POSIX?t, and Using NAs:
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
## this throws error (since NAs are converted to the string NA):
timeDate(paste(dts,tms), FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-29 00:12:55] [2001-01-15 11:34:02] [2004-08-30 10:30:00]
#> [4] [1990-02-09 12:18:23]
## Error in midnightStandard2(charvec, format) :
##   'charvec' has non-NA entries of different number of characters

## these work:
td1 <- timeDate(pasteMat(cbind(dts, tms)), FinCenter = "Europe/Zurich")
td2 <- timeDate(pasteMat(dts, tms), FinCenter = "Europe/Zurich")
identical(td1, td2) ## TRUE
#> [1] TRUE

## timeCalendar
## getRmetricsOptions("currentYear")
timeCalendar()  # 12 months of current year
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]
timeCalendar(2022) # 12 months of 2022
#> GMT
#>  [1] [2022-01-01] [2022-02-01] [2022-03-01] [2022-04-01] [2022-05-01]
#>  [6] [2022-06-01] [2022-07-01] [2022-08-01] [2022-09-01] [2022-10-01]
#> [11] [2022-11-01] [2022-12-01]
timeCalendar(y = c(1989, 2001, 2004, 1990), 
    m = c(9, 1, 8, 2), d = c(28, 15, 30, 9), FinCenter = "GMT")
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]
timeCalendar(y = c(1989, 2001, 2004, 1990),
    m = c(9, 1, 8, 2), d = c(28, 15, 30, 9), FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [2004-08-30 02:00:00]
#> [4] [1990-02-09 01:00:00]

## timeCalendar(h = c(9, 14), min = c(15, 23))
timeCalendar(2022, h = c(9, 14), min = c(15, 23))
#> GMT
#>  [1] [2022-01-01 09:15:00] [2022-02-01 14:23:00] [2022-03-01 09:15:00]
#>  [4] [2022-04-01 14:23:00] [2022-05-01 09:15:00] [2022-06-01 14:23:00]
#>  [7] [2022-07-01 09:15:00] [2022-08-01 14:23:00] [2022-09-01 09:15:00]
#> [10] [2022-10-01 14:23:00] [2022-11-01 09:15:00] [2022-12-01 14:23:00]

## timeSequence
timeSequence(from = "2004-03-12", to = "2004-04-11",
  format = "%Y-%m-%d", FinCenter = "GMT")
#> GMT
#>  [1] [2004-03-12] [2004-03-13] [2004-03-14] [2004-03-15] [2004-03-16]
#>  [6] [2004-03-17] [2004-03-18] [2004-03-19] [2004-03-20] [2004-03-21]
#> [11] [2004-03-22] [2004-03-23] [2004-03-24] [2004-03-25] [2004-03-26]
#> [16] [2004-03-27] [2004-03-28] [2004-03-29] [2004-03-30] [2004-03-31]
#> [21] [2004-04-01] [2004-04-02] [2004-04-03] [2004-04-04] [2004-04-05]
#> [26] [2004-04-06] [2004-04-07] [2004-04-08] [2004-04-09] [2004-04-10]
#> [31] [2004-04-11]
timeSequence(from = "2004-03-12", to = "2004-04-11",
  format = "%Y-%m-%d", FinCenter = "Europe/Zurich")
#> Europe/Zurich
#>  [1] [2004-03-12 01:00:00] [2004-03-13 01:00:00] [2004-03-14 01:00:00]
#>  [4] [2004-03-15 01:00:00] [2004-03-16 01:00:00] [2004-03-17 01:00:00]
#>  [7] [2004-03-18 01:00:00] [2004-03-19 01:00:00] [2004-03-20 01:00:00]
#> [10] [2004-03-21 01:00:00] [2004-03-22 01:00:00] [2004-03-23 01:00:00]
#> [13] [2004-03-24 01:00:00] [2004-03-25 01:00:00] [2004-03-26 01:00:00]
#> [16] [2004-03-27 01:00:00] [2004-03-28 02:00:00] [2004-03-29 02:00:00]
#> [19] [2004-03-30 02:00:00] [2004-03-31 02:00:00] [2004-04-01 02:00:00]
#> [22] [2004-04-02 02:00:00] [2004-04-03 02:00:00] [2004-04-04 02:00:00]
#> [25] [2004-04-05 02:00:00] [2004-04-06 02:00:00] [2004-04-07 02:00:00]
#> [28] [2004-04-08 02:00:00] [2004-04-09 02:00:00] [2004-04-10 02:00:00]
#> [31] [2004-04-11 02:00:00]

## print, summary, format
tC = timeCalendar(2022)
tC
#> GMT
#>  [1] [2022-01-01] [2022-02-01] [2022-03-01] [2022-04-01] [2022-05-01]
#>  [6] [2022-06-01] [2022-07-01] [2022-08-01] [2022-09-01] [2022-10-01]
#> [11] [2022-11-01] [2022-12-01]
print(tC)
#> GMT
#>  [1] [2022-01-01] [2022-02-01] [2022-03-01] [2022-04-01] [2022-05-01]
#>  [6] [2022-06-01] [2022-07-01] [2022-08-01] [2022-09-01] [2022-10-01]
#> [11] [2022-11-01] [2022-12-01]
summary(tC)
#> Start Record: 2022-01-01 
#> End Record:   2022-12-01 
#> Observations: 12 
#> Format:       %Y-%m-%d 
#> FinCenter:    GMT 
#> 
format(tC)
#>  [1] "2022-01-01" "2022-02-01" "2022-03-01" "2022-04-01" "2022-05-01"
#>  [6] "2022-06-01" "2022-07-01" "2022-08-01" "2022-09-01" "2022-10-01"
#> [11] "2022-11-01" "2022-12-01"
```
