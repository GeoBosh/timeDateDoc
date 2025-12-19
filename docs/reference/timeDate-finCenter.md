# Financial Center of a timeDate object

Get or set the financial center of a `"timeDate"` object.

## Usage

``` r
# S4 method for class 'timeDate'
finCenter(x)
# S4 method for class 'timeDate'
finCenter(x) <- value
```

## Arguments

- x:

  a `timeSeries` object.

- value:

  a character with the location of the financial center named as
  "continent/city".

## Details

`"timeDate"` objects store the time in the GMT time zone. The financial
center specifies a location whose local time is to be used to format the
object, e.g., for printing.

`finCenter` gives the financial center associated with a ‘timeDate’
object. The assignment form changes it to the specified value. Both
functions are S4 generics. This page describes the methods defined in
package ‘timeDate’.

## See also

[`listFinCenter`](https://geobosh.github.io/timeDateDoc/reference/timeDate-listFinCenter.md)

## Examples

``` r
date <- timeDate("2008-01-01")
finCenter(date) <- "GMT"
date
#> GMT
#> [1] [2008-01-01]
format(date)
#> [1] "2008-01-01"

finCenter(date) <- "Zurich"
date
#> Zurich
#> [1] [2008-01-01 01:00:00]
format(date)
#> [1] "2008-01-01 01:00:00"
```
