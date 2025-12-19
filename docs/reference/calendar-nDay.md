# n-th n-day dates

Computes the date for the n-th or last occurrence of an n-day in
year/month.

## Usage

``` r
timeNthNdayInMonth(charvec, nday = 1, nth = 1, format = "%Y-%m-%d",
    zone = "", FinCenter = "")

timeLastNdayInMonth(charvec, nday = 1, format = "%Y-%m-%d",
    zone = "", FinCenter = "")
```

## Arguments

- charvec:

  a character vector or object from a class representing time, such as
  `"timeDate"`, `"POSIXlt"`, etc.

- nday:

  an integer vector with entries ranging from `0` (Sunday) to `6`
  (Saturday).

- nth:

  an integer vector numbering the n-th occurence.

- format:

  the format specification of the input character vector.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  “continent/city”.

## Details

`timeNthNdayInMonth` returns the `nth` occurrence of a n-day (nth =
1,...,5) in `year`, `month`.

`timeLastNdayInMonth` returns the last `nday` in `year`, `month`.

## Value

an object of class `"timeDate"`

## See also

[`trunc.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-round.md),

[`timeFirstDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInMonth`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeFirstDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),
[`timeLastDayInQuarter`](https://geobosh.github.io/timeDateDoc/reference/calendar-firstDay.md),

[`timeNdayOnOrAfter`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md),
[`timeNdayOnOrBefore`](https://geobosh.github.io/timeDateDoc/reference/calendar-onOrAfter.md)

## Examples

``` r
## What date is the second Monday in April 2004?
timeNthNdayInMonth("2004-04-01", 1, 2)
#> GMT
#> [1] [2004-04-12]

## What date has the last Tuesday in May, 1996?
timeLastNdayInMonth("1996-05-01", 2)
#> GMT
#> [1] [1996-05-28]
```
