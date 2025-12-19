# Dates of special one-off holidays in the UK

Gives dates of special one-off holidays in the UK.

## Usage

``` r
specialHolidayGB(year = getRmetricsOptions("currentYear"),
                     value = "timeDate", named = FALSE, ...)
```

## Arguments

- year:

  the year(s) for which special holidays are required, a vector
  containing four-digit integer number(s) of the form `CCYY`, e.g.
  `2023`.

- value:

  the class of the returned value. If `"timeDate"`, the default, return
  a `"timeDate"` object, if `""` return a character vector.

- named:

  if `TRUE`, the dates are named, otherwise unnamed.

- ...:

  further arguments for `as.character` when `value = ""`.

## Details

`specialHolidayGB` gives the special Bank holidays in England for the
years specified by argument `year`, such as the Millenium day at the end
of 1999 and significant Royal events. Don't assume that there is at most
one special holiday in a given year, 2022 had two.

Years that do not contain special Bank holidays are omitted. If there
are no special holidays in the specified year(s) the results is a
`"timeDate"` or `"character"` object of length zero.

The holidays are sorted in increasing time order.

Argument `value` controls the class of the result. The default is
`"timeDate"`. The result is a character vector if `value = ""` (the
empty string). In the latter case, further arguments for the
transformation to `character` can be passed in argument `"..."` (e.g.,
`format`).

If argument `named` is `TRUE`, the dates get names asssociated with
them, so one can see which date represents which holiday.

## Value

a `"timeDate"` or a character vector, as requested by argument `value`

## Author

Georgi N. Boshnakov

## Note

While most of the holidays given by the functions with prefix `GBxxx`
are valid for the UK as a whole and they are (or should be) fully
correct for England, there are variations in Scotland, Wales and
Northern Ireland.

Functions containing 'London' in their name refer to the London Stock
Exchange. Currently, the Bank holidays given by those functions are the
same as for England. Actually, the 'official' holidays between 1834 and
1870 were set by the Bank of England. The first Act of Parlament on the
issue is from 1871.

## See also

[`GBSummerBankHoliday`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md)
for functions giving specific regular Bank holidays,

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md)
for all London Stock Exchange holidays (actually, England holidays) in
requested years.

## Examples

``` r
## UK Millenium day
specialHolidayGB(1999)     # as a dateTime object
#> GMT
#> [1] [1999-12-31]
specialHolidayGB(1999, "") # as a character string
#> [1] "1999-12-31"

## 2 special holidays in UK in 2022
specialHolidayGB(2022)     # [2022-06-03] [2022-09-19]
#> GMT
#> [1] [2022-06-03] [2022-09-19]
## what are their names?
specialHolidayGB(2022, named = TRUE)
#> GMT
#> GBQueensPlatinumJubileeDay         GBQueensFuneralDay 
#>               [2022-06-03]               [2022-09-19] 

## the Spring BH is usually on last Monday of May, but not in 2022
dayOfWeek(GBSpringBankHoliday(2020:2024))
#> 2020-05-25 2021-05-31 2022-06-02 2023-05-29 2024-05-27 
#>      "Mon"      "Mon"      "Thu"      "Mon"      "Mon" 

## the above formed a nice 4-day weekend in early June 2022
## (look at the Thu-Fri sequence on 2-3 June)
dayOfWeek(holidayLONDON(2022))
#> 2022-01-03 2022-04-15 2022-04-18 2022-05-02 2022-06-02 2022-06-03 2022-08-29 
#>      "Mon"      "Fri"      "Mon"      "Mon"      "Thu"      "Fri"      "Mon" 
#> 2022-09-19 2022-12-26 2022-12-27 
#>      "Mon"      "Mon"      "Tue" 
```
