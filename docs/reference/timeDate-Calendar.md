# 'timeDate' from calendar atoms

Create a `"timeDate"` object from calendar atoms.

## Usage

``` r
timeCalendar(y = getRmetricsOptions("currentYear"), m = 1:12, d = 1,
    h = 0, min = 0, s = 0,
    zone = "", FinCenter = "")
```

## Arguments

- y, m, d:

  calendar years (e.g. 1997), defaults are 1960, calendar months (1-12),
  defaults are 1, and calendar days (1-31), defaults are 1,  

- h, min, s:

  hours of the days (0-23), defaults are 0, minutes of the days (0-59),
  defaults are 0, and seconds of the days (0-59), defaults are 0.

- zone:

  a character string, denoting the time zone or financial center where
  the data were recorded.

- FinCenter:

  a character with the location of the financial center named as
  "continent/city".

## Value

an object of class `"timeDate"`

## Examples

``` r
## timeCalendar
   
# Current Year:
getRmetricsOptions("currentYear")
#> currentYear 
#>        2025 

# 12 months of current year
timeCalendar() 
#> GMT
#>  [1] [2025-01-01] [2025-02-01] [2025-03-01] [2025-04-01] [2025-05-01]
#>  [6] [2025-06-01] [2025-07-01] [2025-08-01] [2025-09-01] [2025-10-01]
#> [11] [2025-11-01] [2025-12-01]

timeCalendar(m = c(9, 1, 8, 2), d = c(28, 15, 30, 9),
             y = c(1989, 2001, 2004, 1990), FinCenter = "GMT")
#> GMT
#> [1] [1989-09-28] [2001-01-15] [2004-08-30] [1990-02-09]

timeCalendar(m = c(9, 1, 8, 2), d = c(28, 15, 30, 9),
             y = c(1989, 2001, 2004, 1990), FinCenter = "Europe/Zurich")
#> Europe/Zurich
#> [1] [1989-09-28 01:00:00] [2001-01-15 01:00:00] [2004-08-30 02:00:00]
#> [4] [1990-02-09 01:00:00]
             
timeCalendar(h = c(9, 14), min = c(15, 23))
#> GMT
#>  [1] [2025-01-01 09:15:00] [2025-02-01 14:23:00] [2025-03-01 09:15:00]
#>  [4] [2025-04-01 14:23:00] [2025-05-01 09:15:00] [2025-06-01 14:23:00]
#>  [7] [2025-07-01 09:15:00] [2025-08-01 14:23:00] [2025-09-01 09:15:00]
#> [10] [2025-10-01 14:23:00] [2025-11-01 09:15:00] [2025-12-01 14:23:00]
```
