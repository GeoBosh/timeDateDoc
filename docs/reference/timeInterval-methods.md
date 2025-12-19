# Create 'timeInterval' objects

Create objects from class `"timeInterval"`.

## Usage

``` r
timeInterval(left, right, ...)

# S4 method for class 'timeDate,timeDate'
timeInterval(left, right,...)
# S4 method for class 'ANY,ANY'
timeInterval(left, right, ...)             
# S4 method for class 'timeInterval,missing'
timeInterval(left,right,...)

# S4 method for class 'timeDate,missing'
timeInterval(left, right, units = "days", ...)    
# S4 method for class 'Date,missing'
timeInterval(left,right, units = "days", ...)        
# S4 method for class 'POSIXt,missing'
timeInterval(left,right, units = "days", ...)      
# S4 method for class 'missing,Date'
timeInterval(left,right, units = "days", ...)        
# S4 method for class 'missing,POSIXt'
timeInterval(left,right, units = "days", ...)      
# S4 method for class 'missing,timeDate'
timeInterval(left,right, units = "days", ...)
```

## Arguments

- left,right:

  left and right sides of the intervals, typically `"timeDate"` objects
  of equal length. See individual methods for other possibilities.

- units:

  a character string specifying unit of time. Used only when `left` or
  `right` is missing, see section ‘Details’.

- ...:

  further arguments for methods.

## Details

If both, `left` and `right`, are supplied they represent the edges of
the intervals.

If only `left` is specified, each value represents the rounded time
interval corresponding to argument `units`. For example, 2025-10-15
15:25:31 represents the interval `[2025-10-15 15:00, 2025-10-15 16:00)`
when `units = "mins"` and `[2025-10-15 00:00, 2025-10-16 00:00)` when
`units = "days"`.

See
[`trunc`](https://geobosh.github.io/timeDateDoc/reference/base-round.md)
for admissible values of `units` and other details of the truncation.

Analogously, if only `right` is specified, its truncated value is used
for the right edges of the intervals, while the left edges are obtained
by subtracting one time unit from the right edges. In other word, each
value in `right` represents the rounded time interval corresponding to
the previous time unit. For example, 2025-10-15 15:25:31 represents the
interval `[2025-10-15 14:00, 2025-10-15 15:00)` when `units = "mins"`
and `[2025-10-14 00:00, 2025-10-15 00:00)` when `units = "days"`, see
also
[`trunc`](https://geobosh.github.io/timeDateDoc/reference/base-round.md).

## Value

a `"timeInterval"` object

## Author

Georgi N. Boshnakov

## Methods

- `signature(left = "timeDate", right = "timeDate")`:

  creates a `"timeInterval"` object as the union of intervals
  represented by `[left[i],right[i])`. The union is transformed to a
  canonical form with no overlaps between the intervals and no touching
  edges, see class
  `"`[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-class.md)`"`.
  So the order and the number of intervals in the returned object may
  not be as in the input arguments.

- `signature(left = "ANY", right = "ANY")`:

  the default method; the time interval is created from `"timeDate"`
  objects created from `left` and `right` using calls to `timeDate`. All
  `"..."` arguments are passed in both calls to `timeDate`.

- `signature(left = "timeDate", right = "missing")`:

- `signature(left = "Date", right = "missing")`:

- `signature(left = "POSIXt", right = "missing")`:

  convert each element of `left` into an interval containing it and form
  the union. The left edge of each interval is `trunc(left, units)` and
  with corresponding right end `timeCeiling(left, units)`. If a
  date-time is already rounded to `units`, then it is taken as the left
  end of the interval and its right end is the next rounded value.

- `signature(left = "missing", right = "timeDate")`:

- `signature(left = "missing", right = "Date")`:

- `signature(left = "missing", right = "POSIXt")`:

  a time interval, aligned at `unit`, just to the left of the given
  date-times. For example, for `unit = "days"`, the result is the day
  before.

- `signature(left = "timeInterval", right = "missing")`:

## See also

class
`"`[`timeInterval`](https://geobosh.github.io/timeDateDoc/reference/timeInterval-class.md)`"`,

[`in_int`](https://geobosh.github.io/timeDateDoc/reference/in_int.md)
for set operations on `"timeInterval"` objects

## Examples

``` r
timeInterval(left = "2024-12-20", right = "2024-12-21")
#> simple time interval
#> GMT
#> [2024-12-20 -- 2024-12-21)
timeInterval(left = "2024-12-20 10:00", right = "2024-12-21 11:00")
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-21 11:00:00)

timeInterval(left = c("2024-12-20 10:00", "2024-12-22 10:00"),
             right = c("2024-12-21 11:00", "2024-12-23 11:00"))
#> union of 2 time intervals
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-21 11:00:00)
#> [2024-12-22 10:00:00 -- 2024-12-23 11:00:00)

## overlapping or touching intervals are combined
timeInterval(left = c("2024-12-20 10:00", "2024-12-21 10:00"),
             right = c("2024-12-21 11:00", "2024-12-23 11:00"))
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-23 11:00:00)
timeInterval(left = c("2024-12-20 10:00", "2024-12-21 08:00"),
             right = c("2024-12-21 11:00", "2024-12-23 11:00"))
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-23 11:00:00)

## create timeInterval by rounding down and up  times inside the desired unit
timeInterval(as.Date("2024-12-20"))
#> simple time interval
#> GMT
#> [2024-12-20 -- 2024-12-21)
timeInterval(timeDate("2024-12-20 10:20:30"), unit = "days")
#> simple time interval
#> GMT
#> [2024-12-20 -- 2024-12-21)
timeInterval(right = timeDate("2024-12-20 10:20:30"), unit = "days")
#> simple time interval
#> GMT
#> [2024-12-19 -- 2024-12-20)

timeInterval(timeDate("2024-12-20 10:20:30"), unit = "hours")
#> simple time interval
#> GMT
#> [2024-12-20 10:00:00 -- 2024-12-20 11:00:00)
timeInterval(right = timeDate("2024-12-20 10:20:30"), unit = "hours")
#> simple time interval
#> GMT
#> [2024-12-20 09:00:00 -- 2024-12-20 10:00:00)

timeInterval(timeDate("2024-12-20 10:20:30"), unit = "mins")
#> simple time interval
#> GMT
#> [2024-12-20 10:20:00 -- 2024-12-20 10:21:00)
timeInterval(right = timeDate("2024-12-20 10:20:30"), unit = "mins")
#> simple time interval
#> GMT
#> [2024-12-20 10:19:00 -- 2024-12-20 10:20:00)
```
