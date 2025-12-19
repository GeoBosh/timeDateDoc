# Resampling 'timeDate' objects

Resamples a `"timeDate"` object.

## Value

an object of class `"timeDate"`

## Examples

``` r
## c
# Create Character Vectors:
dts = c("1989-09-28", "2001-01-15", "2004-08-30", "1990-02-09")
dts
#> [1] "1989-09-28" "2001-01-15" "2004-08-30" "1990-02-09"
tms = c(  "23:12:55",   "10:34:02",   "08:30:00",   "11:18:23")
tms
#> [1] "23:12:55" "10:34:02" "08:30:00" "11:18:23"
   
## "+/-" 
# Add One Day to a Given timeDate Object:
GMT = timeDate(dts, zone = "GMT", FinCenter = "GMT")
GMT
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]
ZUR = timeDate(dts, zone = "GMT", FinCenter = "Europe/Zurich")
ZUR
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [2004-08-30 02:00:00]
#> [4] [1990-02-09 01:00:00]
   
## c
# Concatenate and Replicate timeDate Objects:
c(GMT[1:2], ZUR[1:2])
#> GMT
#> [1] [1989-09-28] [2001-01-15] [1989-09-28] [2001-01-15]
c(ZUR[1:2], GMT[1:2])
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [1989-09-28 01:00:00]
#> [4] [2001-01-15 01:00:00]
   
## rep
rep(ZUR[2], times = 3)
#> Europe/Zurich
#> [1] [2001-01-15 01:00:00] [2001-01-15 01:00:00] [2001-01-15 01:00:00]
rep(ZUR[2:3], times = 2)  
#> Europe/Zurich
#> [1] [2001-01-15 01:00:00] [2004-08-30 02:00:00] [2001-01-15 01:00:00]
#> [4] [2004-08-30 02:00:00]
```
