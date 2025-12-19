# Length of a 'timeDate' object

Returns the length of a `"timeDate"` object.

## Usage

``` r
# S3 method for class 'timeDate'
length(x)
```

## Arguments

- x:

  an object of class `"timeDate"`.

## Value

an integer of length 1

## Examples

``` r
## timeCalendar
tC = timeCalendar()
   
## length - 
length(tC)
#> [1] 12
```
