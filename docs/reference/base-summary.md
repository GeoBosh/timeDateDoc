# Summary method

Summarizes details of a `"timeDate"` object.

## Usage

``` r
# S3 method for class 'timeDate'
summary(object, ...)
```

## Arguments

- object:

  an object of class `"timeDate"`.

- ...:

  arguments passed to other methods.

## Details

Creates a summary report of the details of a `"timeDate"` object. This
includes the starting and end date, the number of dates the format and
the financial center in use.

## Value

an object from S3 class `"timeDate_summary"`, which has a print method

## Examples

``` r
tC <- timeCalendar()
summary(tC)
#> Start Record: 2025-01-01 
#> End Record:   2025-12-01 
#> Observations: 12 
#> Format:       %Y-%m-%d 
#> FinCenter:    GMT 
#> 
```
