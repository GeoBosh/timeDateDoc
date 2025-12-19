# List of holidays

Returns a list of holidays supported by package `"timeDate"`.

## Usage

``` r
listHolidays(pattern = ".*")
```

## Arguments

- pattern:

  a character string containing a regular expression.

## Details

Gives a character vector containing the names of supported holidays
matching `pattern`. The default is to return all holidays.

The list is sorted alphabetically. It is changed from time to time. So,
the use of character indexing (possibly representing patterns) on the
returned list is strongly recommended.

## Value

a character vector, sorted in alphabetical order

## See also

[`BoxingDay`](https://geobosh.github.io/timeDateDoc/reference/holiday-Dates.md),
etc., for descriptions of the individual holiday functions,

[`holiday`](https://geobosh.github.io/timeDateDoc/reference/holiday.md)
alternative to calling directly individual holiday functions (takes one
or more holiday functions as argument),

[`Easter`](https://geobosh.github.io/timeDateDoc/reference/calendar-Easter.md),

[`holidayLONDON`](https://geobosh.github.io/timeDateDoc/reference/holiday-LONDON.md),
[`holidayNERC`](https://geobosh.github.io/timeDateDoc/reference/holiday-NERC.md),
[`holidayNYSE`](https://geobosh.github.io/timeDateDoc/reference/holiday-NYSE.md),
[`holidayTSX`](https://geobosh.github.io/timeDateDoc/reference/holiday-TSX.md),
[`holidayZURICH`](https://geobosh.github.io/timeDateDoc/reference/holiday-ZURICH.md)
for holidays at major financial centers.

## Examples

``` r
## Local Swiss Holidays:
listHolidays("CH")
#> [1] "CHAscension"        "CHBerchtoldsDay"    "CHConfederationDay"
#> [4] "CHKnabenschiessen"  "CHSechselaeuten"   

listHolidays("Easter")
#> [1] "Easter"       "EasterMonday" "EasterSunday"
listHolidays("NewYear")
#> [1] "DENewYearsEve" "JPNewYearsDay" "NewYearsDay"   "USNewYearsDay"

## All Holidays
listHolidays()
#>   [1] "Advent1st"                          
#>   [2] "Advent2nd"                          
#>   [3] "Advent3rd"                          
#>   [4] "Advent4th"                          
#>   [5] "AllSaints"                          
#>   [6] "AllSouls"                           
#>   [7] "Annunciation"                       
#>   [8] "Ascension"                          
#>   [9] "AshWednesday"                       
#>  [10] "AssumptionOfMary"                   
#>  [11] "BirthOfVirginMary"                  
#>  [12] "BoxingDay"                          
#>  [13] "CACanadaDay"                        
#>  [14] "CACivicProvincialHoliday"           
#>  [15] "CAFamilyDay"                        
#>  [16] "CALabourDay"                        
#>  [17] "CAThanksgivingDay"                  
#>  [18] "CAVictoriaDay"                      
#>  [19] "CHAscension"                        
#>  [20] "CHBerchtoldsDay"                    
#>  [21] "CHConfederationDay"                 
#>  [22] "CHKnabenschiessen"                  
#>  [23] "CHSechselaeuten"                    
#>  [24] "CaRemembranceDay"                   
#>  [25] "CelebrationOfHolyCross"             
#>  [26] "ChristTheKing"                      
#>  [27] "ChristmasDay"                       
#>  [28] "ChristmasEve"                       
#>  [29] "CorpusChristi"                      
#>  [30] "DEAscension"                        
#>  [31] "DEChristmasEve"                     
#>  [32] "DECorpusChristi"                    
#>  [33] "DEGermanUnity"                      
#>  [34] "DENewYearsEve"                      
#>  [35] "Easter"                             
#>  [36] "EasterMonday"                       
#>  [37] "EasterSunday"                       
#>  [38] "Epiphany"                           
#>  [39] "FRAllSaints"                        
#>  [40] "FRArmisticeDay"                     
#>  [41] "FRAscension"                        
#>  [42] "FRAssumptionVirginMary"             
#>  [43] "FRBastilleDay"                      
#>  [44] "FRFetDeLaVictoire1945"              
#>  [45] "GBEarlyMayBankHoliday"              
#>  [46] "GBSpringBankHoliday"                
#>  [47] "GBSummerBankHoliday"                
#>  [48] "GoodFriday"                         
#>  [49] "ITAllSaints"                        
#>  [50] "ITAssumptionOfVirginMary"           
#>  [51] "ITEpiphany"                         
#>  [52] "ITImmaculateConception"             
#>  [53] "ITLiberationDay"                    
#>  [54] "ITStAmrose"                         
#>  [55] "InternationalWomensDay"             
#>  [56] "JPAutumnalEquinox"                  
#>  [57] "JPBankHolidayDec31"                 
#>  [58] "JPBankHolidayJan2"                  
#>  [59] "JPBankHolidayJan3"                  
#>  [60] "JPBunkaNoHi"                        
#>  [61] "JPChildrensDay"                     
#>  [62] "JPComingOfAgeDay"                   
#>  [63] "JPConstitutionDay"                  
#>  [64] "JPEmperorsBirthday"                 
#>  [65] "JPGantan"                           
#>  [66] "JPGreeneryDay"                      
#>  [67] "JPHealthandSportsDay"               
#>  [68] "JPKeirouNoHi"                       
#>  [69] "JPKenkokuKinenNoHi"                 
#>  [70] "JPKenpouKinenBi"                    
#>  [71] "JPKinrouKanshaNoHi"                 
#>  [72] "JPKodomoNoHi"                       
#>  [73] "JPKokuminNoKyujitu"                 
#>  [74] "JPMarineDay"                        
#>  [75] "JPMidoriNoHi"                       
#>  [76] "JPMountainDay"                      
#>  [77] "JPNatFoundationDay"                 
#>  [78] "JPNationHoliday"                    
#>  [79] "JPNationalCultureDay"               
#>  [80] "JPNewYearsDay"                      
#>  [81] "JPRespectForTheAgedDay"             
#>  [82] "JPSeijinNoHi"                       
#>  [83] "JPShuubunNoHi"                      
#>  [84] "JPTaiikuNoHi"                       
#>  [85] "JPTennouTanjyouBi"                  
#>  [86] "JPThanksgivingDay"                  
#>  [87] "JPUmiNoHi"                          
#>  [88] "JPVernalEquinox"                    
#>  [89] "LaborDay"                           
#>  [90] "MassOfArchangels"                   
#>  [91] "NewYearsDay"                        
#>  [92] "PalmSunday"                         
#>  [93] "Pentecost"                          
#>  [94] "PentecostMonday"                    
#>  [95] "PresentationOfLord"                 
#>  [96] "Quinquagesima"                      
#>  [97] "RogationSunday"                     
#>  [98] "Septuagesima"                       
#>  [99] "SolemnityOfMary"                    
#> [100] "TransfigurationOfLord"              
#> [101] "TrinitySunday"                      
#> [102] "USCPulaskisBirthday"                
#> [103] "USChristmasDay"                     
#> [104] "USColumbusDay"                      
#> [105] "USDecorationMemorialDay"            
#> [106] "USElectionDay"                      
#> [107] "USGoodFriday"                       
#> [108] "USInaugurationDay"                  
#> [109] "USIndependenceDay"                  
#> [110] "USJuneteenthNationalIndependenceDay"
#> [111] "USLaborDay"                         
#> [112] "USLincolnsBirthday"                 
#> [113] "USMLKingsBirthday"                  
#> [114] "USMemorialDay"                      
#> [115] "USNewYearsDay"                      
#> [116] "USPresidentsDay"                    
#> [117] "USThanksgivingDay"                  
#> [118] "USVeteransDay"                      
#> [119] "USWashingtonsBirthday"              
#> [120] "specialHolidayGB"                   
```
