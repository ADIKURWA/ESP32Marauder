# clearlist
Clears the list of scanned access points or SSIDs from [scanap](scanap), [ssid](ssid), or [scansta](scansta) respectively.  
It is important to note if the list of access points is cleared, the list of stations will be cleared as well.

## Usage
`clearlist -a/-s/-c`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-a/-s/-c` | Required | Specify list of access points, ssids, or stations to clear |

#### Examples
Clear list of scanned APs: `clearlist -a`  
Clear list of SSIDs: `clearlist -s`    
Clear list of stations: `clearlist -c`
