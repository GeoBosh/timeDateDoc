# Format recognition

Tries to recognize the date/time format.

## Usage

``` r
whichFormat(charvec, silent = FALSE)
```

## Arguments

- charvec:

  a character string or vector of dates and times.

- silent:

  a logical flag. Should a warning be printed if the format cannot be
  recognized?

## Value

a format string

## See also

[`midnightStandard`](https://geobosh.github.io/timeDateDoc/reference/timeDate-midnightStandard.md)

## Examples

``` r
whichFormat("2007-12-31 00:00:00")
#> [1] "%Y-%m-%d %H:%M:%S"
whichFormat("2007-12-31 24:00")
#> [1] "%Y-%m-%d %H:%M"
```
