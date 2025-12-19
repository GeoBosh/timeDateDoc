# System time as 'timeDate' object

Returns the system time as an object of class `"timeDate"`.

## Usage

``` r
Sys.timeDate(FinCenter = "")
```

## Arguments

- FinCenter:

  a character string with the location of the financial center named as
  "continent/city".

## Value

a `"timeDate"` object

## Examples

``` r
if (FALSE) { # \dontrun{
## direct
Sys.timeDate()

## Local Time in Zurich
Sys.timeDate(FinCenter = "Zurich")  

## transformed from "POSIX(c)t" with timeDate()
timeDate(Sys.time()) 
 
## Local Time in Zurich
timeDate(Sys.time(), FinCenter = "Zurich")  
} # }   
```
