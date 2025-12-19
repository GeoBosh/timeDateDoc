# Midnight standard

Corrects `"timeDate"` objects if they do not fulfill the ISO8601
midnight standard.

## Usage

``` r
midnightStandard (charvec, format)
midnightStandard2(charvec, format)
```

## Arguments

- charvec:

  a character string or vector of dates and times.

- format:

  a string, the format specification of the input character vector.

## Details

`midnightStandard2()` calls
[`strptime`](https://rdrr.io/r/base/strptime.html). Since the latter
returns `NA`s for elements that don't conform to the midnight standard,
the inputs corresponding to `NA`s are further processed to fix this.

`midnightStandard()` converts to character vector the result obtained
from `midnightStandard2()`.

## Value

for `midnightStandard`, a `character` vector,

for `midnightStandard2`, a
[`POSIXct`](https://rdrr.io/r/base/DateTimeClasses.html) object with
time zone `"GMT"`.

## See also

[`whichFormat`](https://geobosh.github.io/timeDateDoc/reference/timeDate-whichFormat.md)

## Examples

``` r
ch <- "2007-12-31 24:00"
midnightStandard(ch)
#> [1] "2008-01-01 00:00:00"
(ms2 <- midnightStandard2(ch))
#> [1] "2008-01-01 GMT"
class(ms2)
#> [1] "POSIXct" "POSIXt" 
```
