# Skewness

Functions to compute skewness.

## Usage

``` r
skewness(x, ...)

# Default S3 method
skewness(x, na.rm = FALSE, method = c("moment", "fisher"), ...)

# S3 method for class 'data.frame'
skewness(x, na.rm = FALSE, method = c("moment", "fisher"), ...)

# S3 method for class 'POSIXct'
skewness(x, ...)

# S3 method for class 'POSIXlt'
skewness(x, ...)
```

## Arguments

- x:

  a numeric vector or object.

- na.rm:

  a logical. Should missing values be removed?

- method:

  a character string, the method of computation, see section ‘Detaials’.

- ...:

  arguments to be passed.

## Details

Argument `method` can be one of `"moment"` or `"fisher"`. The `"moment"`
method is based on the definitions of skewness for distributions and
this should be used when resampling (bootstrap or jackknife). The
`"fisher"` method correspond to the usual "unbiased" definition of
sample variance, although in the case of skewness exact unbiasedness is
not possible.

The data frame method computes the skewness of each column.

## Value

a numeric value or vector with attribute `"method"` indicating the
method. For the data frame method the values are named using the columns
names.

## See also

[`kurtosis`](https://geobosh.github.io/timeDateDoc/reference/stats-kurtosis.md)

## Examples

``` r
r = rnorm(100)
mean(r)
#> [1] 0.06014279
var(r)
#> [1] 0.9580954
   
skewness(r)  
#> [1] 0.04923852
#> attr(,"method")
#> [1] "moment"
```
