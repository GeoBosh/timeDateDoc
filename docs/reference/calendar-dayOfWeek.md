# Day of the week

Returns the days of the week of the data in a `"timeDate"` object.

## Usage

``` r
dayOfWeek(x)
```

## Arguments

- x:

  an object of class `"timeDate"`.

## Value

a character vector giving the days of the week corresponding to the
elements of `x`. The names are in English, abbreviated to three letters.

## See also

[`dayOfYear`](https://geobosh.github.io/timeDateDoc/reference/calendar-dayOfYear.md)

## Examples

``` r
## timeCalendar
tC <- timeCalendar(2022)
       
## the days of the year
dayOfWeek(tC)
#> 2022-01-01 2022-02-01 2022-03-01 2022-04-01 2022-05-01 2022-06-01 2022-07-01 
#>      "Sat"      "Tue"      "Tue"      "Fri"      "Sun"      "Wed"      "Fri" 
#> 2022-08-01 2022-09-01 2022-10-01 2022-11-01 2022-12-01 
#>      "Mon"      "Thu"      "Sat"      "Tue"      "Thu" 
```
