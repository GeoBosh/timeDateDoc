# myFinCenter variable

A character string with the name of my financial center.

## Note

Can be modified by the user to his/her own or any other financial
center. The default is `"GMT"`. To list all supported financial centers
use the function `listFinCenter`.

## See also

[`listFinCenter`](https://geobosh.github.io/timeDateDoc/reference/timeDate-listFinCenter.md)

## Examples

``` r
## myFinCenter - the global setting currently used
getRmetricsOptions("myFinCenter")
#> myFinCenter 
#>       "GMT" 
   
## change to another financial center
# setRmetricsOptions(myFinCenter = "Zurich")
   
## Do not care about DST
# setRmetricsOptions(myFinCenter = "GMT") 
```
