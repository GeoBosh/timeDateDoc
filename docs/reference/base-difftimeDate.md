# Difference of two 'timeDate' objects

Returns the difference of two 'timeDate' objects.

## Usage

``` r
difftimeDate(time1, time2, 
    units = c("auto", "secs", "mins", "hours", "days", "weeks"))
```

## Arguments

- time1, time2:

  two objects of class `"timeDate"`.

- units:

  a character string denoting the date/time units in which the results
  are desired.

## Details

`difftimeDate` is analogous to
[`base::difftime`](https://rdrr.io/r/base/difftime.html) for
`"timeDate"` arguments.

`difftimeDate` takes a difference of two `"timeDate"` objects and
returns an object of class `"difftime"` with an attribute indicating the
units.

## Value

an object of class `"difftime"` with an attribute indicating the units

## See also

[`difftime`](https://rdrr.io/r/base/difftime.html),

[`diff.timeDate`](https://geobosh.github.io/timeDateDoc/reference/base-diff.md)
for differencing a `"timeDate"` object.

## Examples

``` r
dts <- c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
GMT <- timeDate(dts, zone = "GMT", FinCenter = "GMT") 
GMT
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]

difftimeDate(GMT[1:2], GMT[-(1:2)])  
#> Time differences in days
#> [1] -5450  3993
```
