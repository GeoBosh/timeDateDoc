# Kurtosis

Generic function for computation of kurtosis. The methods defined in
package timeDate are described here.

## Usage

``` r
kurtosis(x, ...)

# Default S3 method
kurtosis(x, na.rm = FALSE,
                  method = c("excess", "moment", "fisher"), ...)

# S3 method for class 'data.frame'
kurtosis(x, na.rm = FALSE,
                  method = c("excess", "moment", "fisher"), ...)

# S3 method for class 'POSIXct'
kurtosis(x, ...)

# S3 method for class 'POSIXlt'
kurtosis(x, ...)
```

## Arguments

- x:

  a numeric vector or object.

- na.rm:

  a logical. Should missing values be removed?

- method:

  a character string, the method of computation, see section ‘Details’.

- ...:

  arguments to be passed.

## Details

`kurtosis` is an S3 generic function. This page describes the methods
defined in package `dateTime`.

Argument `"method"` can be one of `"moment"`, `"fisher"`, or `"excess"`.
If `"excess"` is selected, then the value of the kurtosis is computed by
the `"moment"` method and a value of 3 will be subtracted. The
`"moment"` method is based on the definitions of kurtosis for
distributions and this method should be used when resampling (bootstrap
or jackknife). The `"fisher"` method corresponds to the usual “unbiased”
definition of sample variance, although in the case of kurtosis exact
unbiasedness is not possible.

If `x` is numeric the kurtosis is computed according to the description
given for argument `method`. A logical vector is treated as a vector of
1's and 0's.

The `data.frame` method applies `kurtosis` recursively to each column.
The `POSIXlt` method computes the kurtosis of the underlying numerical
representation of the date/times. The method for `POSIXct` does the same
after converting the argument to `POSIXlt`.

The default method returns `NA`, with a warning, if it can't handle
argument `x`.

## Value

a numeric value or vector with attribute `"method"` indicating the
method. For the data frame method the values are named using the columns
names.

## See also

[`skewness`](https://geobosh.github.io/timeDateDoc/reference/stats-skewness.md)

## Examples

``` r
r = rnorm(100)
mean(r)
#> [1] 0.1560529
var(r)
#> [1] 1.048539
   
## kurtosis
kurtosis(r)
#> [1] 0.662118
#> attr(,"method")
#> [1] "excess"

kurtosis(data.frame(r = r, r2 = r^2))
#>        r       r2 
#> 0.662118 5.146108 
#> attr(,"method")
#> [1] "excess"
```
