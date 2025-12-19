# First and last days

Computes the first/last day in a given month/quarter.

## Usage

``` r
timeFirstDayInMonth(charvec, format = "%Y-%m-%d", zone = "", 
    FinCenter = "")
timeLastDayInMonth(charvec, format = "%Y-%m-%d", zone = "", 
    FinCenter = "")

timeFirstDayInQuarter(charvec, format = "%Y-%m-%d", zone = "", 
    FinCenter = "")
timeLastDayInQuarter(charvec, format = "%Y-%m-%d", zone = "", 
    FinCenter = "")
```

## Arguments

- charvec:

  a character vector or object from a class representing time, such as
  `"timeDate"`, `"POSIXlt"`, etc.

- format:

  the format specification of the input character vector.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  "continent/city".

## Details

The functions `timeFirstDayInMonth` and `timeLastDayInMonth` return the
first or last day, respectively, in a given month and year.

The same functionality for quarterly time horizons is provided by the
functions `timeFirstDayInQuarter` and `timeLastDayInQuarter`.

If argument `FinCenter` is missing or the empty string and the object is
from a time-date class, it is taken from slot `"FinCenter"` (if charvec
is `"timeDate"`) or from attribute `"tzone"` (if from another time-date
class and not NULL). If all of this fails, `FinCenter` is obtained with
[`getRmetricsOptions`](https://geobosh.github.io/timeDateDoc/reference/options-RmetricsOptions.md).

If `zone` is missing or the empty string, it is set to (the deduced
value for) `FinCenter`.

## Value

an object of class `"timeDate"`

## See also

[`trunc.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),

`timeFirstDayInMonth`, `timeLastDayInMonth`, `timeFirstDayInQuarter`,
`timeLastDayInQuarter`,

[`timeNthNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),
[`timeLastNdayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-nDay.md),

[`timeNdayOnOrAfter`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md),
[`timeNdayOnOrBefore`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md)

## Examples

``` r
## date as character string
charvec <- "2006-04-16"
myFinCenter <- getRmetricsOptions("myFinCenter")

## What date has the last day in a month for a given date?
timeLastDayInMonth(charvec, format = "%Y-%m-%d", 
  zone = myFinCenter, FinCenter = myFinCenter)
#> GMT
#> [1] [2006-04-30]
timeLastDayInMonth(charvec)
#> GMT
#> [1] [2006-04-30]
timeLastDayInMonth(charvec, FinCenter = "Zurich")
#> Zurich
#> [1] [2006-04-30]
   
## What date has the first day in a month for a given date?
timeFirstDayInMonth(charvec)
#> GMT
#> [1] [2006-04-01]
    
## What date has the last day in a quarter for a given date?
timeLastDayInQuarter(charvec)
#> GMT
#> [1] [2006-06-30]
    
## What date has the first day in a quarter for a given date?
timeFirstDayInQuarter(charvec)
#> GMT
#> [1] [2006-04-01]
```
