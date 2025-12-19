# Rmetrics option settings

Allow the user to set and examine a variety of global options which
affect the way in which Rmetrics functions compute and display their
results.

## Usage

``` r
getRmetricsOptions(x, unset = "")
setRmetricsOptions(...)
```

## Arguments

- x:

  a character vector of option names. If missing, give all Rmetrics
  options currently set.

- unset:

  a character vector or a list specifying what values to return for
  options in `x` that are not set (see
  [`mget`](https://rdrr.io/r/base/get.html)).

- ...:

  any options can be defined using `name = value` or by passing a list
  of such tagged values.

## Value

for `getRmetricsOptions`, the value(s) of the requested options,

for `setRmetricsOptions`, the revious value(s) of the options set in the
call, invisibly,
