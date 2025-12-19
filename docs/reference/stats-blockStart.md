# Equally sized 'timeDate' blocks

Creates start (end) dates for equally sized `"timeDate"` blocks.

## Usage

``` r
blockStart(x, block = 20)
blockEnd(x, block = 20)
```

## Arguments

- block:

  an integer value specifying the length in number of records for
  numerically sized blocks of dates.

- x:

  an object of class `"timeDate"`.

## Details

The functions `blockStart` and `blockEnd` create vectors of start and
end values for equally sized `"timeDate"` blocks. Note, the functions
are event counters and not a time counter between measuring time
intervals between start and end dates! For equally sized blocks in time
one has before to align the time stamps in equal time differences.

## Value

an object of class `"timeDate"`

## Examples

``` r
## timeSequence
# 360 Days Series:
tS <- timeSequence(to = "2022-09-23 09:39:23", length.out = 360)
    
## blockStart | blockEnd
Start <- blockStart(tS, 30)
End <- blockEnd(tS, 30)
Start
#> GMT
#>  [1] [2022-08-25 09:39:23] [2022-09-24 09:39:23] [2022-10-24 09:39:23]
#>  [4] [2022-11-23 09:39:23] [2022-12-23 09:39:23] [2023-01-22 09:39:23]
#>  [7] [2023-02-21 09:39:23] [2023-03-23 09:39:23] [2023-04-22 09:39:23]
#> [10] [2023-05-22 09:39:23] [2023-06-21 09:39:23] [2023-07-21 09:39:23]
End
#> GMT
#>  [1] [2022-09-23 09:39:23] [2022-10-23 09:39:23] [2022-11-22 09:39:23]
#>  [4] [2022-12-22 09:39:23] [2023-01-21 09:39:23] [2023-02-20 09:39:23]
#>  [7] [2023-03-22 09:39:23] [2023-04-21 09:39:23] [2023-05-21 09:39:23]
#> [10] [2023-06-20 09:39:23] [2023-07-20 09:39:23] [2023-08-19 09:39:23]
End - Start
#> Time differences in days
#>  [1] 29 29 29 29 29 29 29 29 29 29 29 29
```
