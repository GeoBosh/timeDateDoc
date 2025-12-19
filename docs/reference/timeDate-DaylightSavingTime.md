# Daylight Saving Time Rules

Functions for about 400 cities and regions which return daylight saving
time rules and time zone offsets.

## Details

As a selection of these functions:

Adelaide Algiers Amsterdam Anchorage Andorra Athens Auckland Bahrain
Bangkok Beirut Belfast Belgrade Berlin Bogota Bratislava Brisbane
Brussels Bucharest Budapest BuenosAires Cairo Calcutta Caracas
Casablanca Cayman Chicago Copenhagen Darwin Denver Detroit Dubai Dublin
Eastern Edmonton Frankfurt Helsinki HongKong Honolulu Indianapolis
Istanbul Jakarta Jerusalem Johannesburg Kiev KualaLumpur Kuwait Lagos
Lisbon Ljubljana London LosAngeles Luxembourg Madrid Manila Melbourne
MexicoCity Monaco Montreal Moscow Nairobi Nassau NewYork Nicosia Oslo
Pacific Paris Perth Prague Riga Riyadh Rome Seoul Shanghai Singapore
Sofia Stockholm Sydney Taipei Tallinn Tehran Tokyo Tunis Vaduz Vancouver
Vienna Vilnius Warsaw Winnipeg Zagreb Zurich, ...

## Note

There are currently two synonyms available "Pacific" for Los Angeles and
"Eastern" for New York.

Specific time zones (`AST`, `CET`, `CST`, `EET`, `EST`, `MST` and `PST`)
are also available.

Note we leave the space in all double named cities like New York or Hong
Kong and use an underscore for it.

All the entries are retrieved from the tzdata library which is available
under GNU GPL licence.

## Examples

``` r
## DST rules for Zurich
head(Zurich())
#>                Zurich offSet isdst TimeZone     numeric
#> 1 1853-07-15 23:25:52   1786     0      BMT -3675198848
#> 2 1894-05-31 23:30:14   3600     0      CET -2385246586
#> 3 1941-05-05 00:00:00   7200     1     CEST  -904435200
#> 4 1941-10-06 00:00:00   3600     0      CET  -891129600
#> 5 1942-05-04 00:00:00   7200     1     CEST  -872985600
#> 6 1942-10-05 00:00:00   3600     0      CET  -859680000
tail(Zurich())
#>                  Zurich offSet isdst TimeZone    numeric
#> 239 2097-03-31 01:00:00   7200     1     CEST 4015530000
#> 240 2097-10-27 01:00:00   3600     0      CET 4033674000
#> 241 2098-03-30 01:00:00   7200     1     CEST 4046979600
#> 242 2098-10-26 01:00:00   3600     0      CET 4065123600
#> 243 2099-03-29 01:00:00   7200     1     CEST 4078429200
#> 244 2099-10-25 01:00:00   3600     0      CET 4096573200

## list all available centers
listFinCenter()
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
#> [241] "Europe/Andorra"                 "Europe/Astrakhan"              
#> [243] "Europe/Athens"                  "Europe/Belgrade"               
#> [245] "Europe/Berlin"                  "Europe/Brussels"               
#> [247] "Europe/Bucharest"               "Europe/Budapest"               
#> [249] "Europe/Chisinau"                "Europe/Dublin"                 
#> [251] "Europe/Gibraltar"               "Europe/Helsinki"               
#> [253] "Europe/Istanbul"                "Europe/Kaliningrad"            
#> [255] "Europe/Kirov"                   "Europe/Kyiv"                   
#> [257] "Europe/Lisbon"                  "Europe/London"                 
#> [259] "Europe/Madrid"                  "Europe/Malta"                  
#> [261] "Europe/Minsk"                   "Europe/Moscow"                 
#> [263] "Europe/Paris"                   "Europe/Prague"                 
#> [265] "Europe/Riga"                    "Europe/Rome"                   
#> [267] "Europe/Samara"                  "Europe/Saratov"                
#> [269] "Europe/Simferopol"              "Europe/Sofia"                  
#> [271] "Europe/Tallinn"                 "Europe/Tirane"                 
#> [273] "Europe/Ulyanovsk"               "Europe/Vienna"                 
#> [275] "Europe/Vilnius"                 "Europe/Volgograd"              
#> [277] "Europe/Warsaw"                  "Europe/Zurich"                 
#> [279] "Indian/Chagos"                  "Indian/Maldives"               
#> [281] "Indian/Mauritius"               "Pacific/Apia"                  
#> [283] "Pacific/Auckland"               "Pacific/Bougainville"          
#> [285] "Pacific/Chatham"                "Pacific/Easter_Island"         
#> [287] "Pacific/Efate"                  "Pacific/Fakaofo"               
#> [289] "Pacific/Fiji"                   "Pacific/Galapagos"             
#> [291] "Pacific/Gambier"                "Pacific/Guadalcanal"           
#> [293] "Pacific/Guam"                   "Pacific/Honolulu"              
#> [295] "Pacific/Kanton"                 "Pacific/Kiritimati"            
#> [297] "Pacific/Kosrae"                 "Pacific/Kwajalein"             
#> [299] "Pacific/Marquesas"              "Pacific/Nauru"                 
#> [301] "Pacific/Niue"                   "Pacific/Norfolk"               
#> [303] "Pacific/Noumea"                 "Pacific/Pago_Pago"             
#> [305] "Pacific/Palau"                  "Pacific/Pitcairn"              
#> [307] "Pacific/Port_Moresby"           "Pacific/Rarotonga"             
#> [309] "Pacific/Tahiti"                 "Pacific/Tarawa"                
#> [311] "Pacific/Tongatapu"             
```
