# select
Select or deselect access points and/or stations for targeted attacks. You must provide a comma separated list of indices of the desired access points and/or stations from [list](list).  
Any specified indices which were **NOT** already `selected` will become `selected`. Any specified indices which were already `selected` will no longer be `selected`

## Usage
```select [-a <CSL of target indices>] | [-s <CSL of target indices>] | [-c <CSL of target indices>]```

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-a <CSL of target indices>/all` | Optional | The index numbers of the access points shown with [list](../list) |
| `-s <CSL of target indices>` | Optional | The index numbers of the ssids shown with [list](../list) |
| `-c <CSL of target indices>` | Optional | The index numbers of the stations show with [list](../list) |

#### Examples
`select -a 1,3,5`: Selects APs at indices 1, 3, and 5  
`select -a all`: Selects all APs in the list  
`select -c 3,4,29`: Select stations at indices 3, 4, and 29

