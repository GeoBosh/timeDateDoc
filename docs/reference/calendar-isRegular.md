# Checks if a date/time vector is regular

Checks if a date/time vector is regular. i.e. if it is a daily, a
monthly, or a quarterly date/time vector. If the date/time vector is
regular the frequency can be determined calling the function frequency.

## Usage

``` r
# S4 method for class 'timeDate'
isDaily(x)
# S4 method for class 'timeDate'
isMonthly(x)
# S4 method for class 'timeDate'
isQuarterly(x)

# S4 method for class 'timeDate'
isRegular(x)

# S3 method for class 'timeDate'
frequency(x, ...)
```

## Arguments

- x:

  an object of class `"timeDate"`.

- ...:

  arguments to be passed.

## Details

A date/time vector is defined as daily if the vector has no more than
one date/time stamp per day.

A date/time vector is defined as monthly if the vector has no more than
one date/time stamp per month.

A date/time vector is defined as quarterly if the vector has no more
than one date/time stamp per quarter.

A monthly date/time vector is also a daily vector, a quarterly date/time
vector is also a monthly vector.

A regular date/time vector is either a monthly or a quarterly vector.

NOT yet implemented is the case of weekly vectors.

## Value

for the `is*` functions, `TRUE` or `FALSE` depending on whether the
date/time vector fulfills the condition or not.

`frequency` returns in general 1, for quarterly date/time vectors 4, and
for monthly vectors 12.

## Examples

``` r
tC <- timeCalendar(2023)
tC
#> GMT
#>  [1] [2023-01-01] [2023-02-01] [2023-03-01] [2023-04-01] [2023-05-01]
#>  [6] [2023-06-01] [2023-07-01] [2023-08-01] [2023-09-01] [2023-10-01]
#> [11] [2023-11-01] [2023-12-01]
isRegular(tC)
#> [1] TRUE
frequency(tC)
#> [1] 12

isMonthly(tC)
#> [1] TRUE
isQuarterly(tC)
#> [1] FALSE
isDaily(tC)
#> [1] FALSE
```
