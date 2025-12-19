# Concatenate matrix columns, keeping NAs

Concatenate the columns of a matrix or df. Like paste, but any row
containing one or more NAs gives in an NA in the corresponding element
of the result. Argument `sep` can be a vector, specifying different
separators between different columns.

## Usage

``` r
pasteMat(x, ..., sep = NULL)
```

## Arguments

- x:

  a matrix or data frame. Can also be a vector if one or more ‘...’
  arguments are used.

- ...:

  additional arguments to be combined, together with `x`, with `cbind`.

- sep:

  a character vector of separators between the columns, can be of length
  larger than 1. The default is `sep = " "` (as for `paste`.

## Details

If the `...` arguments are used, they are combined by the equivalent of
`x <- cbind(x, ...)`.

`pasteMat` gives a result similar to the one that would be obtained from
`paste` if the columns of `x` are passed to that individually. The main
difference is in the treatment of `NA`s.

Any row of `x` containing one or more `NA`s results in an `NA` in the
corresponding element of the result.

There can be different separators between the columns. This can be
obtained by setting `sep` to be of length greater than one.

## Value

a character vector

## Author

Georgi N. Boshnakov

## See also

`paste`, `timeDate`

## Examples

``` r
a <- c("a",  NA, "b", NA, "c")
b <- c("x", "y",  NA, NA, "z")

## turns NAs into the string "NA"
paste(a, b)
#> [1] "a x"   "NA y"  "b NA"  "NA NA" "c z"  

## keeps NAs in the result
pasteMat(a, b)
#> [1] "a x" NA    NA    NA    "c z"
pasteMat(cbind(a, b)) # same
#> [1] "a x" NA    NA    NA    "c z"

dts <- c("1989-09-28", NA, "2004-08-30", "1990-02-09")
tms <- c(  "23:12:55",   "10:34:02",   NA,   "11:18:23")

paste(dts, tms)
#> [1] "1989-09-28 23:12:55" "NA 10:34:02"         "2004-08-30 NA"      
#> [4] "1990-02-09 11:18:23"
## this throws error (since NAs are converted to the string NA):
##   timeDate(paste(dts, tms), FinCenter = "Europe/Zurich")

## these work
td1 <- timeDate(pasteMat(cbind(dts, tms)), FinCenter = "Europe/Zurich")
td2 <- timeDate(pasteMat(dts, tms), FinCenter = "Europe/Zurich")       
identical(td1, td2)                                                    
#> [1] TRUE
td1                                                                       
#> Europe/Zurich
#> [1] [1989-09-29 00:12:55] [NA]                  [NA]                 
#> [4] [1990-02-09 12:18:23]
```
