# Format methods

Formats `"timeDate"` objects as ISO conform character strings.

## Usage

``` r
# S3 method for class 'timeDate'
format(x, format = "", tz = "", usetz = FALSE, ...)
```

## Arguments

- format:

  a character string describing the format.

- tz:

  a timezone specification to be used for the conversion.

- usetz:

  a logical.

- x:

  an object of class `"timeDate"`.

- ...:

  arguments passed to other methods.

## Value

an ISO conforming formatted character string

## See also

`as.character`

## Examples

``` r
## timeCalendar
# Time Calendar 16:00
tC = timeCalendar() + 16*3600
tC
#> GMT
#>  [1] [2025-01-01 16:00:00] [2025-02-01 16:00:00] [2025-03-01 16:00:00]
#>  [4] [2025-04-01 16:00:00] [2025-05-01 16:00:00] [2025-06-01 16:00:00]
#>  [7] [2025-07-01 16:00:00] [2025-08-01 16:00:00] [2025-09-01 16:00:00]
#> [10] [2025-10-01 16:00:00] [2025-11-01 16:00:00] [2025-12-01 16:00:00]
   
## format as ISO character string 
format(tC)
#>  [1] "2025-01-01 16:00:00" "2025-02-01 16:00:00" "2025-03-01 16:00:00"
#>  [4] "2025-04-01 16:00:00" "2025-05-01 16:00:00" "2025-06-01 16:00:00"
#>  [7] "2025-07-01 16:00:00" "2025-08-01 16:00:00" "2025-09-01 16:00:00"
#> [10] "2025-10-01 16:00:00" "2025-11-01 16:00:00" "2025-12-01 16:00:00"
```
