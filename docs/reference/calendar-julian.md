# Julian counts and calendar atoms

Returns Julian day counts, date/time atoms from a `"timeDate"` object,
and extracts month atoms from a `"timeDate"` object.

## Usage

``` r
# S3 method for class 'timeDate'
julian(x, origin = timeDate("1970-01-01"), 
       units = c("auto", "secs", "mins", "hours", "days", "weeks"), 
       zone = NULL, FinCenter = NULL, ...)

# S4 method for class 'timeDate'
atoms(x, ...)

# S3 method for class 'timeDate'
months(x, abbreviate = FALSE)

# S3 method for class 'timeDate'
weekdays(x, abbreviate = FALSE)

# S3 method for class 'timeDate'
quarters(x, abbreviate)

# S4 method for class 'timeDate'
x$name
```

## Arguments

- x:

  an object of class `"timeDate"`.

- origin:

  a length-one object inheriting from class `"timeDate"` setting the
  origin for the julian counter.

- units:

  a character string denoting the date/time units in which the results
  are desired.

- zone:

  the time zone or financial center where the data were recorded.

- FinCenter:

  a character string with the location of the financial center named as
  "continent/city".

- abbreviate:

  currently not used.

- name:

  one of `year`, `month`, `day`, `hour`, `minute`, `second`, `wday` (or
  `weekday`), `wday0` (or `weekday0`), and `quarter`. Completion is
  available in interactive sessions.

- ...:

  arguments passed to other methods.

## Details

Generic functions to extract properties of `"timeDate"` objects.
`julian` and `months` are generics from base R, while `atoms` is a
generic defined in this package.

`julian` extracts the number of days since `origin` (can be fractional),
see also [`julian`](https://rdrr.io/r/base/weekday.POSIXt.html).

`atoms` extracts the calendar atoms from a `"timeDate"` object, i.e.,
the year, month, day, and optionally, hour, minute and second. The
result is a data frame with the financial center in atrribute
`"control"`.

`months` extracts the months, see section ‘Note’.

The dollar operator applied to a `"timeDate"` object, e.g. `td$name`,
extracts a component of the date/time values as a numeric vector.
Currently, `name` can be one of `year`, `month`, `day`, `hour`,
`minute`, `second`, `wday` (or `weekday`), `wday0` (or `weekday0`), and
`quarter`. `wday0` (`weekday0`) starts with 0 (for Sunday), the meaning
of the rest should be clear.

In interactive sessions, completion is available for the dollar
operator.

## Value

for `julian`, a `difftime` object;

for `atoms`, a `data.frame` with attribute `"control"` containing the
financial center of the input vector `x`. The data frame has the
following components:

- Y:

  year,

- m:

  month,

- d:

  day,

- H:

  hour,

- M:

  minute,

- S:

  second;

for `months`, a numeric vector with attribute `"control"` containing the
financial center. (**Note:** this use is deprecated, use `$month`
instead.)

for the dollar method, the corresponding component as numeric vector.

## Note

**Deprecation Warning:** a \`timeDate\` method for \`months\` has
existed for a long time but it was returning a numeric vector, which is
inconsistent with the other methods for months in base R (they return
names of months). Returning a numeric vector when 'abbreviate' is
missing is a temporary compromise, to avoid breaking old code but this
should be considered deprecated. Use `td$month` to get the numbers.

## See also

[`dayOfWeek`](https://geobosh.github.io/timeDateDoc/reference/calendar-dayOfWeek.md),
[`dayOfYear`](https://geobosh.github.io/timeDateDoc/reference/calendar-dayOfYear.md);

the base R functions
[`julian`](https://rdrr.io/r/base/weekday.POSIXt.html),
[`difftime`](https://rdrr.io/r/base/difftime.html),
[`months`](https://rdrr.io/r/base/weekday.POSIXt.html);

## Examples

``` r
## julian
tC = timeCalendar(2022)
julian(tC)[1:3]
#> Time differences in days
#> [1] 18993 19024 19052
   
## atoms
atoms(tC)
#>       Y  m d H M S
#> 1  2022  1 1 0 0 0
#> 2  2022  2 1 0 0 0
#> 3  2022  3 1 0 0 0
#> 4  2022  4 1 0 0 0
#> 5  2022  5 1 0 0 0
#> 6  2022  6 1 0 0 0
#> 7  2022  7 1 0 0 0
#> 8  2022  8 1 0 0 0
#> 9  2022  9 1 0 0 0
#> 10 2022 10 1 0 0 0
#> 11 2022 11 1 0 0 0
#> 12 2022 12 1 0 0 0
   
## months
tC$month   # recommended 1 to 12
#>  [1]  1  2  3  4  5  6  7  8  9 10 11 12
months(tC) # deprecated - will be changed to return month names, as base::months()
#>  [1]  1  2  3  4  5  6  7  8  9 10 11 12
#> attr(,"control")
#> FinCenter 
#>     "GMT" 

weekdays(tC)
#>  [1] "Saturday"  "Tuesday"   "Tuesday"   "Friday"    "Sunday"    "Wednesday"
#>  [7] "Friday"    "Monday"    "Thursday"  "Saturday"  "Tuesday"   "Thursday" 
weekdays(tC, TRUE)
#>  [1] "Sat" "Tue" "Tue" "Fri" "Sun" "Wed" "Fri" "Mon" "Thu" "Sat" "Tue" "Thu"

## the dollar method
tC$year
#>  [1] 2022 2022 2022 2022 2022 2022 2022 2022 2022 2022 2022 2022
tC$month
#>  [1]  1  2  3  4  5  6  7  8  9 10 11 12
tC$day
#>  [1] 1 1 1 1 1 1 1 1 1 1 1 1
tC$hour
#>  [1] 0 0 0 0 0 0 0 0 0 0 0 0
tC$minute
#>  [1] 0 0 0 0 0 0 0 0 0 0 0 0
tC$second
#>  [1] 0 0 0 0 0 0 0 0 0 0 0 0
tC$weekday
#>  [1] 6 2 2 5 7 3 5 1 4 6 2 4
tC$weekday0
#>  [1] 6 2 2 5 0 3 5 1 4 6 2 4

tC$quarter
#>  [1] "Q1" "Q1" "Q1" "Q2" "Q2" "Q2" "Q3" "Q3" "Q3" "Q4" "Q4" "Q4"
```
