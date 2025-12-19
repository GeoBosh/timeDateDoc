# List of financial centers

Lists supported financial centers.

## Usage

``` r
listFinCenter(pattern = ".*")
```

## Arguments

- pattern:

  a pattern character string as required by the
  [`grep`](https://rdrr.io/r/base/grep.html) function. The default,
  `".*"`, gives all supported financial centers

## Details

The list returned by `listFinCenter` doesn't contain all financial
centers supported by timeDate. Rather it contains currently supported
‘standard names’ of time zones defined in the tz (a.k.a. Zoneinfo)
database. Names supported by previous versions of by timeDate are
recognised, even though they are not in the list.

## Value

a character vector listing the financial centers whose names match
`pattern`.

## See also

[`rulesFinCenter`](https://geobosh.github.io/timeDateDoc/reference/timeDate-rulesFinCenter.md)
for the daylight saving rules

## Examples

``` r
## myFinCenter - the global setting currently used
getRmetricsOptions("myFinCenter")
#> myFinCenter 
#>       "GMT" 

## Other Financial Centers
listFinCenter("Asia/")
#>  [1] "Asia/Almaty"        "Asia/Amman"         "Asia/Anadyr"       
#>  [4] "Asia/Aqtau"         "Asia/Aqtobe"        "Asia/Ashgabat"     
#>  [7] "Asia/Atyrau"        "Asia/Baghdad"       "Asia/Baku"         
#> [10] "Asia/Bangkok"       "Asia/Barnaul"       "Asia/Beirut"       
#> [13] "Asia/Bishkek"       "Asia/Chita"         "Asia/Choibalsan"   
#> [16] "Asia/Colombo"       "Asia/Damascus"      "Asia/Dhaka"        
#> [19] "Asia/Dili"          "Asia/Dubai"         "Asia/Dushanbe"     
#> [22] "Asia/Famagusta"     "Asia/Gaza"          "Asia/Hebron"       
#> [25] "Asia/Ho_Chi_Minh"   "Asia/Hong_Kong"     "Asia/Hovd"         
#> [28] "Asia/Irkutsk"       "Asia/Jakarta"       "Asia/Jayapura"     
#> [31] "Asia/Jerusalem"     "Asia/Kabul"         "Asia/Kamchatka"    
#> [34] "Asia/Karachi"       "Asia/Kathmandu"     "Asia/Khandyga"     
#> [37] "Asia/Kolkata"       "Asia/Krasnoyarsk"   "Asia/Kuching"      
#> [40] "Asia/Macau"         "Asia/Magadan"       "Asia/Makassar"     
#> [43] "Asia/Manila"        "Asia/Nicosia"       "Asia/Novokuznetsk" 
#> [46] "Asia/Novosibirsk"   "Asia/Omsk"          "Asia/Oral"         
#> [49] "Asia/Pontianak"     "Asia/Pyongyang"     "Asia/Qatar"        
#> [52] "Asia/Qostanay"      "Asia/Qyzylorda"     "Asia/Riyadh"       
#> [55] "Asia/Sakhalin"      "Asia/Samarkand"     "Asia/Seoul"        
#> [58] "Asia/Shanghai"      "Asia/Singapore"     "Asia/Srednekolymsk"
#> [61] "Asia/Taipei"        "Asia/Tashkent"      "Asia/Tbilisi"      
#> [64] "Asia/Tehran"        "Asia/Thimphu"       "Asia/Tokyo"        
#> [67] "Asia/Tomsk"         "Asia/Ulaanbaatar"   "Asia/Urumqi"       
#> [70] "Asia/Ust-Nera"      "Asia/Vladivostok"   "Asia/Yakutsk"      
#> [73] "Asia/Yangon"        "Asia/Yekaterinburg" "Asia/Yerevan"      
listFinCenter("^A")    # all beginning with "A"
#>   [1] "Africa/Abidjan"                 "Africa/Algiers"                
#>   [3] "Africa/Bissau"                  "Africa/Cairo"                  
#>   [5] "Africa/Casablanca"              "Africa/Ceuta"                  
#>   [7] "Africa/El_Aaiun"                "Africa/Johannesburg"           
#>   [9] "Africa/Juba"                    "Africa/Khartoum"               
#>  [11] "Africa/Lagos"                   "Africa/Maputo"                 
#>  [13] "Africa/Monrovia"                "Africa/Nairobi"                
#>  [15] "Africa/Ndjamena"                "Africa/Sao_Tome"               
#>  [17] "Africa/Tripoli"                 "Africa/Tunis"                  
#>  [19] "Africa/Windhoek"                "America/Adak"                  
#>  [21] "America/Anchorage"              "America/Araguaina"             
#>  [23] "America/Argentina/Buenos_Aires" "America/Argentina/Catamarca"   
#>  [25] "America/Argentina/Cordoba"      "America/Argentina/Jujuy"       
#>  [27] "America/Argentina/La_Rioja"     "America/Argentina/Mendoza"     
#>  [29] "America/Argentina/Rio_Gallegos" "America/Argentina/Salta"       
#>  [31] "America/Argentina/San_Juan"     "America/Argentina/San_Luis"    
#>  [33] "America/Argentina/Tucuman"      "America/Argentina/Ushuaia"     
#>  [35] "America/Asuncion"               "America/Bahia"                 
#>  [37] "America/Bahia_Banderas"         "America/Barbados"              
#>  [39] "America/Belem"                  "America/Belize"                
#>  [41] "America/Boa_Vista"              "America/Bogota"                
#>  [43] "America/Boise"                  "America/Cambridge_Bay"         
#>  [45] "America/Campo_Grande"           "America/Cancun"                
#>  [47] "America/Caracas"                "America/Cayenne"               
#>  [49] "America/Chicago"                "America/Chihuahua"             
#>  [51] "America/Costa_Rica"             "America/Cuiaba"                
#>  [53] "America/Danmarkshavn"           "America/Dawson"                
#>  [55] "America/Dawson_Creek"           "America/Denver"                
#>  [57] "America/Detroit"                "America/Edmonton"              
#>  [59] "America/Eirunepe"               "America/El_Salvador"           
#>  [61] "America/Fort_Nelson"            "America/Fortaleza"             
#>  [63] "America/Glace_Bay"              "America/Goose_Bay"             
#>  [65] "America/Grand_Turk"             "America/Guatemala"             
#>  [67] "America/Guayaquil"              "America/Guyana"                
#>  [69] "America/Halifax"                "America/Havana"                
#>  [71] "America/Hermosillo"             "America/Indiana/Indianapolis"  
#>  [73] "America/Indiana/Knox"           "America/Indiana/Marengo"       
#>  [75] "America/Indiana/Petersburg"     "America/Indiana/Tell_City"     
#>  [77] "America/Indiana/Vevay"          "America/Indiana/Vincennes"     
#>  [79] "America/Indiana/Winamac"        "America/Inuvik"                
#>  [81] "America/Iqaluit"                "America/Jamaica"               
#>  [83] "America/Juneau"                 "America/Kentucky/Louisville"   
#>  [85] "America/Kentucky/Monticello"    "America/La_Paz"                
#>  [87] "America/Lima"                   "America/Los_Angeles"           
#>  [89] "America/Maceio"                 "America/Managua"               
#>  [91] "America/Manaus"                 "America/Martinique"            
#>  [93] "America/Matamoros"              "America/Mazatlan"              
#>  [95] "America/Menominee"              "America/Merida"                
#>  [97] "America/Metlakatla"             "America/Mexico_City"           
#>  [99] "America/Miquelon"               "America/Moncton"               
#> [101] "America/Monterrey"              "America/Montevideo"            
#> [103] "America/New_York"               "America/Nome"                  
#> [105] "America/Noronha"                "America/North_Dakota/Beulah"   
#> [107] "America/North_Dakota/Center"    "America/North_Dakota/New_Salem"
#> [109] "America/Nuuk"                   "America/Ojinaga"               
#> [111] "America/Panama"                 "America/Paramaribo"            
#> [113] "America/Phoenix"                "America/Port-au-Prince"        
#> [115] "America/Porto_Velho"            "America/Puerto_Rico"           
#> [117] "America/Punta_Arenas"           "America/Rankin_Inlet"          
#> [119] "America/Recife"                 "America/Regina"                
#> [121] "America/Resolute"               "America/Rio_Branco"            
#> [123] "America/Santarem"               "America/Santiago"              
#> [125] "America/Santo_Domingo"          "America/Sao_Paulo"             
#> [127] "America/Scoresbysund"           "America/Sitka"                 
#> [129] "America/St_Johns"               "America/Swift_Current"         
#> [131] "America/Tegucigalpa"            "America/Thule"                 
#> [133] "America/Tijuana"                "America/Toronto"               
#> [135] "America/Vancouver"              "America/Whitehorse"            
#> [137] "America/Winnipeg"               "America/Yakutat"               
#> [139] "America/Yellowknife"            "Antarctica/Casey"              
#> [141] "Antarctica/Davis"               "Antarctica/Macquarie"          
#> [143] "Antarctica/Mawson"              "Antarctica/Palmer"             
#> [145] "Antarctica/Rothera"             "Antarctica/Troll"              
#> [147] "Asia/Almaty"                    "Asia/Amman"                    
#> [149] "Asia/Anadyr"                    "Asia/Aqtau"                    
#> [151] "Asia/Aqtobe"                    "Asia/Ashgabat"                 
#> [153] "Asia/Atyrau"                    "Asia/Baghdad"                  
#> [155] "Asia/Baku"                      "Asia/Bangkok"                  
#> [157] "Asia/Barnaul"                   "Asia/Beirut"                   
#> [159] "Asia/Bishkek"                   "Asia/Chita"                    
#> [161] "Asia/Choibalsan"                "Asia/Colombo"                  
#> [163] "Asia/Damascus"                  "Asia/Dhaka"                    
#> [165] "Asia/Dili"                      "Asia/Dubai"                    
#> [167] "Asia/Dushanbe"                  "Asia/Famagusta"                
#> [169] "Asia/Gaza"                      "Asia/Hebron"                   
#> [171] "Asia/Ho_Chi_Minh"               "Asia/Hong_Kong"                
#> [173] "Asia/Hovd"                      "Asia/Irkutsk"                  
#> [175] "Asia/Jakarta"                   "Asia/Jayapura"                 
#> [177] "Asia/Jerusalem"                 "Asia/Kabul"                    
#> [179] "Asia/Kamchatka"                 "Asia/Karachi"                  
#> [181] "Asia/Kathmandu"                 "Asia/Khandyga"                 
#> [183] "Asia/Kolkata"                   "Asia/Krasnoyarsk"              
#> [185] "Asia/Kuching"                   "Asia/Macau"                    
#> [187] "Asia/Magadan"                   "Asia/Makassar"                 
#> [189] "Asia/Manila"                    "Asia/Nicosia"                  
#> [191] "Asia/Novokuznetsk"              "Asia/Novosibirsk"              
#> [193] "Asia/Omsk"                      "Asia/Oral"                     
#> [195] "Asia/Pontianak"                 "Asia/Pyongyang"                
#> [197] "Asia/Qatar"                     "Asia/Qostanay"                 
#> [199] "Asia/Qyzylorda"                 "Asia/Riyadh"                   
#> [201] "Asia/Sakhalin"                  "Asia/Samarkand"                
#> [203] "Asia/Seoul"                     "Asia/Shanghai"                 
#> [205] "Asia/Singapore"                 "Asia/Srednekolymsk"            
#> [207] "Asia/Taipei"                    "Asia/Tashkent"                 
#> [209] "Asia/Tbilisi"                   "Asia/Tehran"                   
#> [211] "Asia/Thimphu"                   "Asia/Tokyo"                    
#> [213] "Asia/Tomsk"                     "Asia/Ulaanbaatar"              
#> [215] "Asia/Urumqi"                    "Asia/Ust-Nera"                 
#> [217] "Asia/Vladivostok"               "Asia/Yakutsk"                  
#> [219] "Asia/Yangon"                    "Asia/Yekaterinburg"            
#> [221] "Asia/Yerevan"                   "Atlantic/Azores"               
#> [223] "Atlantic/Bermuda"               "Atlantic/Canary"               
#> [225] "Atlantic/Cape_Verde"            "Atlantic/Faroe"                
#> [227] "Atlantic/Madeira"               "Atlantic/South_Georgia"        
#> [229] "Atlantic/Stanley"               "Australia/Adelaide"            
#> [231] "Australia/Brisbane"             "Australia/Broken_Hill"         
#> [233] "Australia/Darwin"               "Australia/Eucla"               
#> [235] "Australia/Hobart"               "Australia/Lindeman"            
#> [237] "Australia/Lord_Howe"            "Australia/Melbourne"           
#> [239] "Australia/Perth"                "Australia/Sydney"              
listFinCenter("^[^A]") # all *not* beginning with "A"
#>  [1] "Europe/Andorra"        "Europe/Astrakhan"      "Europe/Athens"        
#>  [4] "Europe/Belgrade"       "Europe/Berlin"         "Europe/Brussels"      
#>  [7] "Europe/Bucharest"      "Europe/Budapest"       "Europe/Chisinau"      
#> [10] "Europe/Dublin"         "Europe/Gibraltar"      "Europe/Helsinki"      
#> [13] "Europe/Istanbul"       "Europe/Kaliningrad"    "Europe/Kirov"         
#> [16] "Europe/Kyiv"           "Europe/Lisbon"         "Europe/London"        
#> [19] "Europe/Madrid"         "Europe/Malta"          "Europe/Minsk"         
#> [22] "Europe/Moscow"         "Europe/Paris"          "Europe/Prague"        
#> [25] "Europe/Riga"           "Europe/Rome"           "Europe/Samara"        
#> [28] "Europe/Saratov"        "Europe/Simferopol"     "Europe/Sofia"         
#> [31] "Europe/Tallinn"        "Europe/Tirane"         "Europe/Ulyanovsk"     
#> [34] "Europe/Vienna"         "Europe/Vilnius"        "Europe/Volgograd"     
#> [37] "Europe/Warsaw"         "Europe/Zurich"         "Indian/Chagos"        
#> [40] "Indian/Maldives"       "Indian/Mauritius"      "Pacific/Apia"         
#> [43] "Pacific/Auckland"      "Pacific/Bougainville"  "Pacific/Chatham"      
#> [46] "Pacific/Easter_Island" "Pacific/Efate"         "Pacific/Fakaofo"      
#> [49] "Pacific/Fiji"          "Pacific/Galapagos"     "Pacific/Gambier"      
#> [52] "Pacific/Guadalcanal"   "Pacific/Guam"          "Pacific/Honolulu"     
#> [55] "Pacific/Kanton"        "Pacific/Kiritimati"    "Pacific/Kosrae"       
#> [58] "Pacific/Kwajalein"     "Pacific/Marquesas"     "Pacific/Nauru"        
#> [61] "Pacific/Niue"          "Pacific/Norfolk"       "Pacific/Noumea"       
#> [64] "Pacific/Pago_Pago"     "Pacific/Palau"         "Pacific/Pitcairn"     
#> [67] "Pacific/Port_Moresby"  "Pacific/Rarotonga"     "Pacific/Tahiti"       
#> [70] "Pacific/Tarawa"        "Pacific/Tongatapu"    
listFinCenter(".*/L")  # cities with L*
#>  [1] "Africa/Lagos"                "America/Argentina/La_Rioja" 
#>  [3] "America/Kentucky/Louisville" "America/La_Paz"             
#>  [5] "America/Lima"                "America/Los_Angeles"        
#>  [7] "Australia/Lindeman"          "Australia/Lord_Howe"        
#>  [9] "Europe/Lisbon"               "Europe/London"              

stopifnot(identical(sort(listFinCenter()), ## 'A' and 'not A' == everything:
     sort(union(listFinCenter("^A"),
         listFinCenter("^[^A]")))))
```
