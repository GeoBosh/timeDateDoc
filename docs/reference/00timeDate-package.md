# Calendar and date utilities and tools

Package of calendar, date, time tools and utilities for Rmetrics.

The documentation of package ‘timeDate’, rendered with ‘pkgdown’, is
available at [timeDateDoc](https://geobosh.github.io/timeDateDoc/).

## Overview of Topics

This help file describes the concepts and methods behind the S4
`"timeDate"` class used in Rmetrics for financial data and time
management together with the management of public and ecclesiastical
holidays.

The `"timeDate"` class fulfils the conventions of the ISO 8601 standard
as well as of the ANSI C and POSIX standards. Beyond these standards it
provides the "Financial Center" concept which allows to handle data
records collected in different time zones and mix them up to have always
the proper time stamps with respect to your personal financial center,
or alternatively to the GMT reference time. It can thus also handle time
stamps from historical data records from the same time zone, even if the
financial centers changed day light saving times at different calendar
dates.

Moreover `"timeDate"` is almost compatible with the `"timeDate"` class
in Insightful's SPlus `"timeDate"` class. If you move between the two
worlds of R and SPlus, you will not have to rewrite your code. This is
important for business applications.

The `"timeDate"` class offers not only date and time functionality but
it also offers sophisticated calendar manipulations for business days,
weekends, public and ecclesiastical holidays.

This help page is presented in four sections:

1\. S4 `"timeDate"` Class and Functions  
2. Operations on `"timeDate"` Objects  
3. Daylight Saving Time and Financial Centers  
4. Holidays and Holiday Calendars

## 1. S4 `"timeDate"` Class and Generator Functions

Date and time stamps are represented by an S4 object of class
`"timeDate"`.

        setClass("timeDate",
        representation(
        Data = "POSIXct",
        format = "character",
        FinCenter = "character"
        ))
      

They have three slots. The `@Data` slot holds the time stamps which are
`POSIXct` formatted as specified in the `@format` slot. The time stamps
are local and belong to the financial center expressed through the slot
`@FinCenter`.

There are several possibilities to generate a `"timeDate"` object. The
most forward procedure is to use one of the following functions:  

`timeDate` – Creates a `"timeDate"` object from scratch,  
`timeSequence` – creates a sequence of `"timeDate"` objects,  
`timeCalendar` – creates a `"timeDate"` object from calendar atoms,  
`Sys.timeDate` – returns the current date and time as a `"timeDate"`
object.  

With the function `timeDate` you can create `"timeDate"` objects from
scratch by specifying a character vector of time stamps and a financial
center which the character vector belongs to. "GMT" is used by default
as the reference for all date/time operations. But you can set the
variable `myFinCenter` to your local financial center reference if you
want to reference dates/time to it.  

Examples:

        # Show My local Financial Center - Note, by Default this is "GMT"
        getRmetricsOptions("myFinCenter")

        # Compose Character Vectors of Dates and Times:
        Dates <- c("1989-09-28","2001-01-15","2004-08-30","1990-02-09")
        Times <- c(  "23:12:55",  "10:34:02",  "08:30:00",  "11:18:23")
        charvec = paste(Dates, Times)

        # Create a 'timeDate' object
        timeDate(charvec)

        # Create a 'timeDate' object with my financial center set to Zurich
        myFinCenter <- "Zurich"
        timeDate(charvec)

        # if the 'timeDate' was recorded in a different financial center, it
        # will be automatically converted to your financial center,
        # i.e. "Zurich".
        timeDate(charvec, zone = "Tokyo")

        # You can also convert a recorded 'timeDate' from your financial
        # center "Zurich" to another one, for example "NewYork".
        timeDate(charvec, FinCenter = "NewYork")
      

NOTE: Rmetrics has implemented an automated date/time format identifier
for many common date/time formats which tries to automatically recognise
the format for the character vector of dates and times. You can have a
look at  
`whichFormat(charvec)`.  

NOTE: Rmetrics always uses the midnight standard on dates and times. You
can see it with  
`.midnightStandard("2008-01-31 24:00:00")`  

Alternatively we can create a sequence of `"timeDate"` objects with the
help of the function `timeSequence`. This can be done in several ways,
either by specifying the range of the data through the arguments `from`
and `to`, or when `from` is missing, by setting the argument
`length.out` of the desired series. Note in the case of a monthly
sequence, you have further options. For example you can generate the
series with the first or last day in each month, or use more complex
rules like the last or n-th Friday in every month.  

Examples:

        # Lets work in an international environment:
        setRmetricsOptions(myFinCenter = "GMT")

        # Your 'timeDate' is now in the Financial Center "GMT"
        timeDate(charvec)

        # Daily January 2008 Sequence:
        timeSequence(from = "2008-01-01", to = "2008-01-31", by = "day")

        # Monthly 2008 Sequence:
        tS = timeSequence(from = "2008-01-01", to = "2008-12-31", by = "month")
        tS

        # Do you want the last Day or the last Friday in Month Data ?
        timeLastDayInMonth(tS)
        timeLastNdayInMonth(tS, nday = 5)
      

A third possibility is to create `"timeDate"` objects from calendar
atoms. You can specify values or vectors of equal length of integers
denoting year, month, day, hour, minute and seconds. If every day has
the same time stamp, you can just add an offset.  

Examples:

        # Monthly calendar for Current Year
        getRmetricsOptions("currentYear")
        timeCalendar()

        # Daily 'timeDate' for January data from Tokyo local time 16:00
        timeCalendar(2008, m=1, d=1:31, h=16, zone="Tokyo", FinCenter="Zurich")

        # Or add16 hours in seconds ...
        timeCalendar(2008, m=1, d=1:31, zone="Tokyo", FinCenter="Zurich") + 16*3600
      

## 2. Operations on `"timeDate"` Objects

Many operations can be performed on `"timeDate"` objects. You can add
and subtract, round and truncate, subset, coerce or transform them to
other objects. These are only few options among many others.  

**Math Operations**

Math operations can add and subtract dates and times, and perform
logical operations on `"timeDate"` objects.  

Examples:

        # Date and Time Now:
        now = Sys.timeDate()

        # One Hour Later:
        now + 3600

        # Which date/time is earlier or later ?
        tC = timeCalendar()
        tR = tC + round(3600*rnorm(12))
        tR > tC
      

**Lagging**

You can generate suitable lagged and iterated differences:  

`diff.timeDate` – Returns suitably lagged and iterated differences.  

Examples:

        # Monthly Dates 2008 and January 2009:
        tC = c(timeCalendar(2008), timeCalendar(2009)[1])

        # Number of days in months and total 2008:
        diff(tC)
        sum(as.integer(diff(tC)))
      

**Rounding and Truncating**

Dates and times can be rounded or truncated. This is useful lower
frequencies than seconds, for example hourly.  

`round` – rounds objects of class `"timeDate"`,  
`trunc` – truncates objects of class `"timeDate"`.  

Examples:

        # Round the Random Time Stamps to the Nearest Hour:
        tC = timeCalendar()
        tR = tC + round(3600*rnorm(12))
        tR
        round(tR, "h")

        # Truncate by Hour or to the Next Full Hour::
        trunc(tR, "h")
        trunc(tR + 3600, "h")
      

**Subsetting**

Subsetting a `"timeDate"` is a very important issue in the management of
dates and times. Rmetrics offers several functions which are useful in
this context:  

`"["` – Extracts or replaces subsets from `"timeDate"` objects,  
`window` – extract a piece from a `"timeDate"` object,  

In this context it is also important to know the `start` and the `end`
time stamp together with the total number of time stamps.  

`start` – extracts the first entry of a `"timeDate"` object,  
`end` – extracts the last entry of a `"timeDate"` object,  
`length` – returns the length of a `"timeDate"` object.  

Examples:

        # Create Monthly Calendar for next year
        tC = timeCalendar(getRmetricsOptions("currentYear") + 1)
        tC

        # Start, end and length of 'timeDate' objects
        start(tC)
        end(tC)
        length(tC)

        # The first Quarter - Several Alternative Solutions:
        tC[1:3]
        tC[-(4:length(tC))]
        window(tC, start = tC[1], end = tC[3])
        tC[tC < tC[4]]

        # The Quarterly Series:
        tC[seq(3, 12, by = 3)]

        
        
        
        
        
      

Weekdays, weekends, business days, and holidays can be easily obtained
with the following functions:  

`isWeekday` – tests if a date is a weekday or not,  
`isWeekend` – tests if a date is a weekend day or not,  
`isBizday` – tests if a date is a business day or not,  
`isHoliday` – tests if a date is a holiday day or not.  

Examples:

        # A 'timeDate' Sequence around Easter 2008
        Easter(2008)
        tS <- timeSequence(Easter(2008, -14), Easter(2008, +14))
        tS

        # Subset weekdays and business days:
        tW <- tS[isWeekday(tS)]; tW
        dayOfWeek(tW)
        tB <- tS[isBizday(tS, holidayZURICH())]; tB
        dayOfWeek(tB)
      

The functions `blockStart` and `blockEnd` gives time stamps for equally
sized blocks.  

`blockStart` – Creates start dates for equally sized blocks,  
`blockEnd` – Creates end dates for equally sized blocks.  

Examples:

        # 'timeDate' object for the last 365 days:
        tS = timeSequence(length.out = 360)
        tS

        # Subset Pointers for blocks of exactly 30 days:
        blockStart(tS, 30)
        blockEnd(tS, 30)
        Sys.timeDate()
      

**Coercions and Transformations**

`"timeDate"` objects are not living in an isolated world. Coercions and
transformations allow `"timeDate"` objects to communicate with other
formatted time stamps. Be aware that in most cases information can be
lost if the other date.time classes do not support this functionality.
There exist several methods to coerce and transform `"timeDate"` objects
into other objects.  

`as.timeDate` – Implements Use Method,  
`as.timeDate.default` – default Method,  
`as.timeDate.POSIXt` – returns a 'POSIX' object as `"timeDate"`
object,  
`as.timeDate.Date` – returns a 'POSIX' object as `"timeDate"` object.  

`as.character.timeDate` – Returns a `"timeDate"` object as 'character'
string,  
`as.double.timeDate` – returns a `"timeDate"` object as 'numeric'
object,  
`as.data.frame.timeDate` – returns a `"timeDate"` object as 'data.frame'
object,  
`as.POSIXct.timeDate` – returns a `"timeDate"` object as 'POSIXct'
object,  
`as.POSIXlt.timeDate` – returns a `"timeDate"` object as 'POSIXlt'
object,  
`as.Date.timeDate` – returns a `"timeDate"` object as 'Date' object.  

Users or maintainers of other date/time classes can add their own
generic functions. For example `as.timeDate.zoo` and
`as.zoo.timeDate`.  

**Concatenations and Reorderings**

It might be sometimes useful to concatenate or reorder `"timeDate"`
objects. The generic functions to concatenate, replicate, sort,
re-sample, unify and revert a `"timeDate"` objects are :  

`c` – Concatenates `"timeDate"` objects,  
`rep` – replicates a `"timeDate"` object,  
`sort` – sorts a `"timeDate"` object,  
`sample` – resamples a `"timeDate"` object,  
`unique` – makes a `"timeDate"` object unique,  
`rev` – reverts a `"timeDate"` object.  

NOTE: The function `c` of a `"timeDate"` objects takes care of possible
different financial centers specific to each object to be concatenated.
In such cases, all time stamps will be transformed to the financial
center of the first time stamp used in the concatenation:  

Examples:

        # Concatenate the local time stamps to Zurich time ...
        ZH = timeDate("2008-01-01 16:00:00", zone = "GMT", FinCenter = "Zurich")
        NY = timeDate("2008-01-01 18:00:00", zone = "GMT", FinCenter = "NewYork")
        c(ZH, NY)
        c(NY, ZH)

        # Rordering:
        tC = timeCalendar(); tC
        tS = sample(tC); tS
        tO = sort(tS); tO
        tV = rev(tO); tV
        tU = unique(c(tS, tS)); tU
      

## 3. Daylight Saving Time and Financial Centers

Each financial center worldwide has a function which returns Daylight
Saving Time Rules. Almost 400 prototypes are made available through the
Olson time zone data base. The cities and regions can be listed using
the command `listFinCenter`. The DST rules for specific financial center
can be viewed by their name, e.g.
[`Zurich()`](https://geobosh.github.io/timeDateDoc/reference/timeDate-DaylightSavingTime.md).
Additional financial centers can be added by the user taking care of the
format specification of the DST functions.  

**Setting Financial Centers**

All time stamps are handled according to the time zone and daylight
saving time rules specified by the center through the variable
`myFinCenter`. This variable is set by default to `"GMT"` but can be
changed to your local financial center or to any other financial center
you want to use.  

NOTE: By setting the financial center to a continent/city which lies
outside of the time zone used by your computer does not change any time
settings or environment variables used by your computer.  

To change the name of a financial center from one setting to another
just assign to the variable `myFinCenter` the desired name of the city:

Examples:

        # What is my current Financial Center ?
        getRmetricsOptions("myFinCenter")

        # Change to Zurich:
        setRmetricsOptions(myFinCenter = "Zurich")
        getRmetricsOptions("myFinCenter")
      

From now on, all dates and times are handled within the middle European
time zone and the DST rules which are valid for Zurich.

**List of Financial Centers**

There are many other financial centers supported by Rmetrics. They can
be displayed by the function `listFinCenter`. You can also display
partial lists with wildcards and regular expressions:

Examples:

        # List all supported Financial Centers Worldwide:
        listFinCenter()

        # List European Financial Centers:
        listFinCenter("Europe/*")
      

**DST Rules**

For each financial center a function is available. It keeps the
information of the time zones and the DST rules. The functions return a
data.frame with 4Columns :

        Zurich offSet isdst TimeZone
        ...
        62  2008-03-30 01:00:00   7200     1     CEST
        63  2008-10-26 01:00:00   3600     0      CET
        ...
      

The first column describes when the time was changed, the second gives
the offset to "GMT", the third returns the daylight savings time flag
which is positive if in force, zero if not, and negative if unknown. The
last column gives the name of the time zone. You can have a look at the
function
[`Zurich()`](https://geobosh.github.io/timeDateDoc/reference/timeDate-DaylightSavingTime.md)
:  

Examples:

        # Show the DST Rules for Zurich:
        Zurich()

        # List European Financial Centers:
        listFinCenter("Europe/*")
      

## 3. Holidays and Holiday Calendars

It is non-trivial to implement function for business days, weekends and
holidays. It is not difficult in an algorithmic sense, but it can become
tedious to implement the rules of the calendar themselves, for example
the date of Easter.

In the following section we briefly summarise the functions which can
calculate dates of ecclesiastical and public holidays. With the help of
these functions we can also create business and holiday calendars.

**Special Dates:**

The implemented functions can compute the last day in a given month and
year, the dates in a month that is a n-day (e.g. n- = Sun) on or after a
given date, the dates in a month that is a n-day on or before a
specified date, the n-th occurrences of a n-day for a specified
year/month vectors, or the last n-day for a specified year/month value
or vector.  

NOTE: n-days are numbered from 0 to 6 where 0 correspond to the Sunday
and 6 to the Saturday.  

`timeFirstDayInMonth` – Computes the first day in a given month and
year,  
`timeLastDayInMonth` – Computes the last day in a given month and
year,  
`timeFirstDayInQuarter` – Computes the first day in a given quarter and
year,  
`timeLastDayInQuarter` – Computes the last day in a given quarter and
year,  

`timeNdayOnOrAfter` – Computes date that is a "on-or-after" n-day,  
`timeNdayOnOrBefore` –b Computes date that is a "on-or-before" n-day,  

`timeNthNdayInMonth` – Computes n-th occurrence of a n-day in
year/month,  
`timeLastNdayInMonth` – Computes the last n-day in year/month.  

**Holidays:**

Holidays may have two origins: ecclesiastical or public/federal. The
ecclesiastical calendars of Christian churches are based on cycles of
movable and immovable feasts. Christmas, December 25, is the principal
immovable feast. Easter is the principal movable feast, and dates of
most of the other movable feasts are determined with respect to Easter.
However, the movable feasts of the Advent and Epiphany seasons are
Sundays reckoned from Christmas and the Feast of the Epiphany,
respectively.

Examples:

        # List Holidays available in Rmetrics
        listHolidays()

        # The date of Easter for the next 5 years:
        currentYear <- getRmetricsOptions("currentYear")
        Easter(currentYear:(currentYear+5))
      

**Holiday Calendars:**

`holidayZURICH` – Zurich Business Calendar,  
`holidayNYSE` – NYSE Stock Exchange Holiday Calendar,  
`holidayZURICH` – TSX Holiday Calendar.  

We would like to thank all Rmetrics users who gave us many additional
information concerning local holidays.

## References

Bateman R., (2000); *Time Functionality in the Standard C Library*,
Novell AppNotes, September 2000 Issue, 73–85.

Becker R.A., Chambers J.M., Wilks A.R. (1988); *The New S Language*,
Wadsworth & Brooks/Cole.

ISO-8601, (1988); *Data Elements and Interchange Formats - Information
Interchange, Representation of Dates and Time*, International
Organization for Standardization, Reference Number ISO 8601, 14 pages.

James D.A., Pregibon D. (1992), *Chronological Objects for Data
Analysis*, Reprint.

Ripley B.D., Hornik K. (2001); *Date-Time Classes*, R-News, Vol. 1/2
June 2001, 8–12.

Zivot, E., Wang J. (2003); *Modeling Financial Time Series with S-Plus*,
Springer, New-York.
