# Holiday dates

Returns the date of a holiday.

## Usage

``` r
holiday(year = getRmetricsOptions("currentYear"), Holiday = "Easter", 
        ..., names = FALSE)
```

## Arguments

- Holiday:

  one or more names of holidays as a character vector or a list of the
  unquoted function names.

- year:

  an integer value or vector of years, formatted as `YYYY`.

- ...:

  further arguments, currently ignored.

- names:

  if `TRUE` include holiday names.

## Value

an object of class `"timeDate"`

## Details

The package contains functions for most ecclesiastical and public
holidays in the G7 countries and Switzerland.

Easter is the central ecclesiastical holiday. Many other holidays are
related to this feast. The function `Easter` computes the dates of
Easter and related ecclesiastical holidays for the requested year
vector.

`holiday` calculates the dates of ecclesiastical or publich holidays in
the G7 countries, e.g. `holiday(2003, "GoodFriday")`.

Rmetrics contains holiday functions automatically loaded at startup
time. The user can add easily additional holiday functions.

If `names` is TRUE the returned dates will be named. If `Holiday` is
named, its names are used. Otherwise, if `Holiday` is a character
vector, it is used for the names. If the holidays are specified as
unquoted symbols, those are turned into strings for the names. As a lost
resort, if the names cannot be inferred, generated names are used, see
the examples. Note that the names will be duplicated, unless
`length(year) == 1`.

## Overview

The following ecclesiastical and public `[HOLIDAY]` functions in the G7
countries and Switzerland are available:  

*Holidays Related to Easter:*

Septuagesima, Quinquagesima, AshWednesday, PalmSunday, GoodFriday,
EasterSunday, Easter, EasterMonday, RogationSunday, Ascension,
Pentecost, PentecostMonday, TrinitySunday CorpusChristi.  

*Holidays Related to Christmas:*

ChristTheKing, Advent1st, Advent1st, Advent3rd, Advent4th, ChristmasEve,
ChristmasDay, BoxingDay, NewYearsDay.  

*Other Ecclestical Feasts:*

SolemnityOfMary, Epiphany, PresentationOfLord, Annunciation,
TransfigurationOfLord, AssumptionOfMary, AssumptionOfMary,
BirthOfVirginMary, CelebrationOfHolyCross, MassOfArchangels, AllSaints,
AllSouls.  

*CHZurich - Public Holidays:*

CHBerchtoldsDay, CHSechselaeuten, CHAscension, CHConfederationDay,
CHKnabenschiessen.  

*GBLondon - Public Holidays:*

GBEarlyMayBankHoliday, GBSpringBankHoliday GBSummerBankHoliday,
GBNewYearsEve.

(GBMayDay and GBBankHoliday have been removed. Use GBEarlyMayBankHoliday
and GBSpringBankHoliday, respectively)  

*DEFrankfurt - Public Holidays:*

DEAscension, DECorpusChristi, DEGermanUnity, DEChristmasEve,
DENewYearsEve.  

*FRParis - Public Holidays:*

FRFetDeLaVictoire1945, FRAscension, FRBastilleDay,
FRAssumptionVirginMary, FRAllSaints, FRArmisticeDay.  

*ITMilano - Public Holidays:*

ITEpiphany, ITLiberationDay, ITRepublicAnniversary,
ITAssumptionOfVirginMary, ITAllSaints, ITWWIVictoryAnniversary,
ITStAmrose, ITImmaculateConception.  

*USNewYork/USChicago - Public Holidays:*

USNewYearsDay, USInaugurationDay, USMLKingsBirthday, USLincolnsBirthday,
USWashingtonsBirthday, USMemorialDay, USIndependenceDay, USLaborDay,
USColumbusDay, USElectionDay, USVeteransDay, USThanksgivingDay,
USChristmasDay, USCPulaskisBirthday, USGoodFriday,
USJuneteenthNationalIndependenceDay.  

*CAToronto/CAMontreal - Public Holidays:*

CAVictoriaDay, CACanadaDay, CACivicProvincialHoliday, CALabourDay,
CAThanksgivingDay, CaRemembranceDay.  

*JPTokyo/JPOsaka - Public Holidays:*

JPNewYearsDay, JPGantan, JPBankHolidayJan2, JPBankHolidayJan3,
JPComingOfAgeDay, JPSeijinNoHi, JPNatFoundationDay, JPKenkokuKinenNoHi,
JPGreeneryDay, JPMidoriNoHi, JPConstitutionDay, JPKenpouKinenBi,
JPNationHoliday, JPKokuminNoKyujitu, JPChildrensDay, JPKodomoNoHi,
JPMarineDay, JPUmiNoHi, JPRespectForTheAgedDay, JPKeirouNoHi,
JPAutumnalEquinox, JPShuubun-no-hi, JPHealthandSportsDay, JPTaiikuNoHi,
JPNationalCultureDay, JPBunkaNoHi, JPThanksgivingDay,
JPKinrouKanshaNohi, JPKinrou-kansha-no-hi, JPEmperorsBirthday,
JPTennou-tanjyou-bi, JPTennou-tanjyou-bi.  
JPMountainDay

## See also

[`BoxingDay`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md),
etc., for descriptions of the individual holiday functions,

[`listHolidays`](https://geobosh.github.io/timeDateDoc/reference/holiday-Listing.md)
for a list (character vector) of all holidays,

[`Easter`](https://geobosh.github.io/timeDateDoc/reference/calendar-Easter.md),

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
[`holidayZURICH`](https://geobosh.github.io/timeDateDoc/reference/holiday-ZURICH.md)
for holidays at major financial centers.

## Examples

``` r
## holiday
# Dates for GoodFriday from 2000 until 2005:
holiday(2000:2005, "GoodFriday")                  
#> GMT
#> [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#> [6] [2005-03-25]
holiday(2000:2005, GoodFriday) # same (GoodFriday is a function)
#> GMT
#> [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#> [6] [2005-03-25]

# Good Friday and Easter
holiday(2000:2005, c("GoodFriday", "Easter"))                  
#> GMT
#>  [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#>  [6] [2005-03-25] [2000-04-23] [2001-04-15] [2002-03-31] [2003-04-20]
#> [11] [2004-04-11] [2005-03-27]
holiday(2000:2005, c(GoodFriday, Easter))                  
#> GMT
#>  [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#>  [6] [2005-03-25] [2000-04-23] [2001-04-15] [2002-03-31] [2003-04-20]
#> [11] [2004-04-11] [2005-03-27]
   
## Easter   
Easter(2000:2005)
#> GMT
#> [1] [2000-04-23] [2001-04-15] [2002-03-31] [2003-04-20] [2004-04-11]
#> [6] [2005-03-27]

## GoodFriday
GoodFriday(2000:2005)
#> GMT
#> [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#> [6] [2005-03-25]
Easter(2000:2005, -2) 
#> GMT
#> [1] [2000-04-21] [2001-04-13] [2002-03-29] [2003-04-18] [2004-04-09]
#> [6] [2005-03-25]

#### Named holidays

## single year
holiday(2025, Holiday = "Easter", names = TRUE)
#> GMT
#>       Easter 
#> [2025-04-20] 
holiday(2025, Holiday = Easter, names = TRUE)
#> GMT
#>       Easter 
#> [2025-04-20] 

## more years
holiday(2024:2025, Holiday = "Easter", names = TRUE)
#> GMT
#>       Easter       Easter 
#> [2024-03-31] [2025-04-20] 
holiday(2024:2025, Holiday = Easter, names = TRUE)
#> GMT
#>       Easter       Easter 
#> [2024-03-31] [2025-04-20] 

## more than one holiday
holiday(2024:2025, Holiday = c("Easter", "ChristmasDay"), names = TRUE)
#> GMT
#>       Easter       Easter ChristmasDay ChristmasDay 
#> [2024-03-31] [2025-04-20] [2024-12-25] [2025-12-25] 
holiday(2024:2025, Holiday = c(Easter, ChristmasDay), names = TRUE)
#> GMT
#>       Easter       Easter ChristmasDay ChristmasDay 
#> [2024-03-31] [2025-04-20] [2024-12-25] [2025-12-25] 

## holidays in a variable containing character values
ho1 <- "Easter"
holiday(2025, Holiday = ho1, names = TRUE)
#> GMT
#>       Easter 
#> [2025-04-20] 


## here, Easter is evaluated and holiday() doesn't see the name
ho1a <- Easter
ho3 <- c(Easter, GBEarlyMayBankHoliday)

holiday(2025, Holiday = ho1a, names = TRUE)
#> GMT
#>         ho1a 
#> [2025-04-20] 

## if you wish/need to use a separate variable, use 'quote':
ho1b <- quote(Easter)
ho3b <- quote(c(Easter, GBEarlyMayBankHoliday))

holiday(2025, Holiday = ho1b, names = TRUE)
#> GMT
#>       Easter 
#> [2025-04-20] 
holiday(2025, Holiday = ho3b, names = TRUE)
#> GMT
#>                Easter GBEarlyMayBankHoliday 
#>          [2025-04-20]          [2025-05-05] 
holiday(2024:2025, Holiday = ho3b, names = TRUE)
#> GMT
#>                Easter                Easter GBEarlyMayBankHoliday 
#>          [2024-03-31]          [2025-04-20]          [2024-05-06] 
#> GBEarlyMayBankHoliday 
#>          [2025-05-05] 

## with string values there is no need to quote:
ho2 <- c("Easter", "GBEarlyMayBankHoliday")
holiday(2025, Holiday = ho2, names = TRUE)
#> GMT
#>                Easter GBEarlyMayBankHoliday 
#>          [2025-04-20]          [2025-05-05] 




holiday(Holiday = c(Easter, GBEarlyMayBankHoliday), names = TRUE)
#> GMT
#>                Easter GBEarlyMayBankHoliday 
#>          [2025-04-20]          [2025-05-05] 


holiday(2024:2025, Holiday = tmp2, names = TRUE)
#> Error: object 'tmp2' not found
holiday(2024:2025, Holiday = tmp1a, names = TRUE)
#> Error: object 'tmp1a' not found
holiday(2024:2025, Holiday = tmp1, names = TRUE)
#> Error: object 'tmp1' not found


## redundant c() but no harm done
holiday(2024:2025, Holiday = c("Easter"), names = TRUE)
#> GMT
#>       Easter       Easter 
#> [2024-03-31] [2025-04-20] 
holiday(2024:2025, Holiday = c(Easter), names = TRUE)
#> GMT
#>       Easter       Easter 
#> [2024-03-31] [2025-04-20] 
```
