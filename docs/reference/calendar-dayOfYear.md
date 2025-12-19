# Day of the year

Returns the days of the year of the data in a `"timeDate"` object.

## Usage

``` r
dayOfYear(x)
```

## Arguments

- x:

  an object of class `"timeDate"`.

## Value

vector of integers representing the number of days since the beginning
of the year. For January, 1st it is one.

## See also

[`dayOfWeek`](https://geobosh.github.io/timeDateDoc/reference/calendar-dayOfWeek.md)

## Examples

``` r
## timeCalendar
tC <- timeCalendar(2022)
       
## the days of the year
dayOfYear(tC)
#> 2022-01-01 2022-02-01 2022-03-01 2022-04-01 2022-05-01 2022-06-01 2022-07-01 
#>          1         32         60         91        121        152        182 
#> 2022-08-01 2022-09-01 2022-10-01 2022-11-01 2022-12-01 
#>        213        244        274        305        335 
```
