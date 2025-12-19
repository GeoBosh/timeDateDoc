# Endpoints indexes

Returns endpoint indexes from a `"timeDate"` object.

## Usage

``` r
.endpoints(x, on = c("months", "years", "quarters", "weeks", "days",
    "hours", "minutes", "seconds"), k=1)
```

## Arguments

- x:

  a `"timeDate"` object.

- on:

  the periods endpoints to find as a character string. Select from:
  `"months"`, `"years"`, `"quarters"`, `"weeks"`, `"days"`, `"hours"`,
  `"minutes"`, `"seconds"`.

- k:

  along every k-th element.

## Details

`.endpoints` returns an integer vector corresponding to the last
observation in each period specified by `on`, with a zero added to the
beginning of the vector, and the index of the last observation in `x` at
the end.

## Value

an integer vector of endpoints beginning with 0 and ending with the
value equal to the length of the `x` argument

## Author

Jeff Ryan, modified by Diethelm Wuertz for `"timeDate"` objects.

## Examples

``` r
## endpoints

# Weekly Endpoints
.endpoints(timeCalendar(), on="w")
#>  [1]  0  1  2  3  4  5  6  7  8  9 10 11 12
```
