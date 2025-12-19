# Public and ecclesiastical holidays

A collection of functions giving holiday dates in the G7 countries and
Switzerland.

## Usage

``` r
Septuagesima(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

Quinquagesima(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

AshWednesday(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

PalmSunday(year = getRmetricsOptions("currentYear"), 
           value = "timeDate", na_drop = TRUE, ...)

GoodFriday(year = getRmetricsOptions("currentYear"), 
           value = "timeDate", na_drop = TRUE, ...)

EasterSunday(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

EasterMonday(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

RogationSunday(year = getRmetricsOptions("currentYear"), 
               value = "timeDate", na_drop = TRUE, ...)

Ascension(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

Pentecost(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

PentecostMonday(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

TrinitySunday(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

CorpusChristi(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

ChristTheKing(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

Advent1st(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

Advent2nd(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

Advent3rd(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

Advent4th(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

ChristmasEve(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

ChristmasDay(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

BoxingDay(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

NewYearsDay(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

SolemnityOfMary(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

Epiphany(year = getRmetricsOptions("currentYear"), value = "timeDate", 
         na_drop = TRUE, ...)

PresentationOfLord(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

Annunciation(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

TransfigurationOfLord(year = getRmetricsOptions("currentYear"), 
                      value = "timeDate", na_drop = TRUE, ...)

AssumptionOfMary(year = getRmetricsOptions("currentYear"), 
                 value = "timeDate", na_drop = TRUE, ...)

BirthOfVirginMary(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

CelebrationOfHolyCross(year = getRmetricsOptions("currentYear"), 
                       value = "timeDate", na_drop = TRUE, ...)

MassOfArchangels(year = getRmetricsOptions("currentYear"), 
                 value = "timeDate", na_drop = TRUE, ...)

AllSaints(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

AllSouls(year = getRmetricsOptions("currentYear"), value = "timeDate", 
         na_drop = TRUE, ...)

LaborDay(year = getRmetricsOptions("currentYear"), value = "timeDate", 
         na_drop = TRUE, ...)

CHBerchtoldsDay(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

CHSechselaeuten(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

CHAscension(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

CHConfederationDay(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

CHKnabenschiessen(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

GBEarlyMayBankHoliday(year = getRmetricsOptions("currentYear"), 
                      value = "timeDate", na_drop = TRUE, ...)

GBSpringBankHoliday(year = getRmetricsOptions("currentYear"), 
                    value = "timeDate", na_drop = TRUE, ...)

GBSummerBankHoliday(year = getRmetricsOptions("currentYear"), 
                    value = "timeDate", na_drop = TRUE, ...)

DEAscension(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

DECorpusChristi(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

DEGermanUnity(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

DEChristmasEve(year = getRmetricsOptions("currentYear"), 
               value = "timeDate", na_drop = TRUE, ...)

DENewYearsEve(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

FRFetDeLaVictoire1945(year = getRmetricsOptions("currentYear"), 
                      value = "timeDate", na_drop = TRUE, ...)

FRAscension(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

FRBastilleDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

FRAssumptionVirginMary(year = getRmetricsOptions("currentYear"), 
                       value = "timeDate", na_drop = TRUE, ...)

FRAllSaints(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

FRArmisticeDay(year = getRmetricsOptions("currentYear"), 
               value = "timeDate", na_drop = TRUE, ...)

ITEpiphany(year = getRmetricsOptions("currentYear"), 
           value = "timeDate", na_drop = TRUE, ...)

ITLiberationDay(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

ITAssumptionOfVirginMary(year = getRmetricsOptions("currentYear"), 
                         value = "timeDate", na_drop = TRUE, ...)

ITAllSaints(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

ITStAmrose(year = getRmetricsOptions("currentYear"), 
           value = "timeDate", na_drop = TRUE, ...)

ITImmaculateConception(year = getRmetricsOptions("currentYear"), 
                       value = "timeDate", na_drop = TRUE, ...)

USDecorationMemorialDay(year = getRmetricsOptions("currentYear"), 
                        value = "timeDate", na_drop = TRUE, ...)

USPresidentsDay(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

USNewYearsDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

USInaugurationDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

USMLKingsBirthday(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

USLincolnsBirthday(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

USWashingtonsBirthday(year = getRmetricsOptions("currentYear"), 
                      value = "timeDate", na_drop = TRUE, ...)

USMemorialDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

USIndependenceDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

USLaborDay(year = getRmetricsOptions("currentYear"), 
           value = "timeDate", na_drop = TRUE, ...)

USColumbusDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

USElectionDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

USVeteransDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

USThanksgivingDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

USChristmasDay(year = getRmetricsOptions("currentYear"), 
               value = "timeDate", na_drop = TRUE, ...)

USCPulaskisBirthday(year = getRmetricsOptions("currentYear"), 
                    value = "timeDate", na_drop = TRUE, ...)

USGoodFriday(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

USJuneteenthNationalIndependenceDay(
                                    year = getRmetricsOptions("currentYear"), 
                                    value = "timeDate", na_drop = TRUE, 
                                    ...)

CAVictoriaDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

CACanadaDay(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

CACivicProvincialHoliday(year = getRmetricsOptions("currentYear"), 
                         value = "timeDate", na_drop = TRUE, ...)

CALabourDay(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

CAThanksgivingDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

CaRemembranceDay(year = getRmetricsOptions("currentYear"), 
                 value = "timeDate", na_drop = TRUE, ...)

JPVernalEquinox(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

JPNewYearsDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

JPGantan(year = getRmetricsOptions("currentYear"), value = "timeDate", 
         na_drop = TRUE, ...)

JPBankHolidayJan2(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPBankHolidayJan3(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPComingOfAgeDay(year = getRmetricsOptions("currentYear"), 
                 value = "timeDate", na_drop = TRUE, ...)

JPSeijinNoHi(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

JPNatFoundationDay(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

JPKenkokuKinenNoHi(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

JPGreeneryDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

JPMidoriNoHi(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

JPConstitutionDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPKenpouKinenBi(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

JPNationHoliday(year = getRmetricsOptions("currentYear"), 
                value = "timeDate", na_drop = TRUE, ...)

JPKokuminNoKyujitu(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

JPChildrensDay(year = getRmetricsOptions("currentYear"), 
               value = "timeDate", na_drop = TRUE, ...)

JPKodomoNoHi(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

JPMarineDay(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

JPUmiNoHi(year = getRmetricsOptions("currentYear"), value = "timeDate", 
          na_drop = TRUE, ...)

JPRespectForTheAgedDay(year = getRmetricsOptions("currentYear"), 
                       value = "timeDate", na_drop = TRUE, ...)

JPMountainDay(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

JPAutumnalEquinox(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPShuubunNoHi(year = getRmetricsOptions("currentYear"), 
              value = "timeDate", na_drop = TRUE, ...)

JPHealthandSportsDay(year = getRmetricsOptions("currentYear"), 
                     value = "timeDate", na_drop = TRUE, ...)

JPTaiikuNoHi(year = getRmetricsOptions("currentYear"), 
             value = "timeDate", na_drop = TRUE, ...)

JPNationalCultureDay(year = getRmetricsOptions("currentYear"), 
                     value = "timeDate", na_drop = TRUE, ...)

JPBunkaNoHi(year = getRmetricsOptions("currentYear"), 
            value = "timeDate", na_drop = TRUE, ...)

JPThanksgivingDay(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPKinrouKanshaNoHi(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

JPEmperorsBirthday(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

JPTennouTanjyouBi(year = getRmetricsOptions("currentYear"), 
                  value = "timeDate", na_drop = TRUE, ...)

JPBankHolidayDec31(year = getRmetricsOptions("currentYear"), 
                   value = "timeDate", na_drop = TRUE, ...)

InternationalWomensDay(year = getRmetricsOptions("currentYear"),
                       value = "timeDate", na_drop = TRUE, ...)
```

## Arguments

- year:

  an integer value or vector of year numbers (four digits, e.g.,
  `2024`).

- value:

  the class of the returned value. If `"timeDate"`, the default, return
  a `"timeDate"` object, otherwise return a character vector.

- na_drop:

  how to treat `NA`s, `TRUE`, `FALSE` or a character string, see section
  ‘Details’.

- ...:

  further arguments for `format.timeDate`, most notably `"format"`.
  Ignored if `value = "timeDate"`.

## Details

This help page discusses the public and ecclesiastical holidays per se.
Some holidays fall by definition on a working day or a particular day of
the week. For holidays that fall on weekends, many countries have rules
to declare a close by weekday a holiday. The functions here do not
consider such issues but they are handled by the `holidayXXX` functions
(e.g., `holidayLONDON`), see their help pages.

Public holidays change over time as new ones are introduced, dropped or
move to different days. When a holiday date is requested for a year when
it did not exist, what should be returned? The same question arises when
the information is not available in this package.

The ecclesiastical holidays are computed by traditional rules and in
practice should be correct for all years.

Traditionally, package timeDate was computing the dates of the holidays
according to the current rules. In versions of package timeDate greater
than 4022.108 historical information was added for England and Japan
holidays. The updated functions return the dates according to the rules
for the particular years.

For future years the returned dates are always computed accoding to the
current rules.

For years before the first available rules, the default is to use those
rules, whether the holiday existed or not.

Argument `na_drop` can be used to control this. If `na_drop` is `TRUE`,
an entry will not be incuded in the result at all. If `na_drop` is
`FALSE` the value for years when the holiday didn't exist will be `NA`.
If it is a character string, the default, the closest available rules
will be used.

Not all functions respect argument `na_drop`. In that case they act as
if `na_drop` is a character string.

`GBMayDay` and `GBBankHoliday` have been removed. Use
`GBEarlyMayBankHoliday` and `GBSpringBankHoliday`, respectively.

## Note

The holiday information for most countries is incomplete. Contributions
are welcome. Please include references for your sources, whenever
possible.

## Value

the date of the requested holiday as a `"timeDate"` object

## See also

[`holiday`](https://geobosh.github.io/timeDateDoc/reference/holiday.md)
alternative to calling directly individual holiday functions (takes one
or more holiday functions as argument),

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
# Sechselaeuten a half Day Bank Holiday in Switzerland
CHSechselaeuten(2000:2010)
#> GMT
#>  [1] [2000-04-17] [2001-04-16] [2002-04-15] [2003-04-21] [2004-04-19]
#>  [6] [2005-04-18] [2006-04-17] [2007-04-16] [2008-04-21] [2009-04-20]
#> [11] [2010-04-19]
CHSechselaeuten(getRmetricsOptions("currentYear"))
#> GMT
#> [1] [2025-04-21]

## German Unification Day:
DEGermanUnity(getRmetricsOptions("currentYear"))
#> GMT
#> [1] [2025-10-03]
```
