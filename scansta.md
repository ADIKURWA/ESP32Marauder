# scansta
Does a scan of wireless stations/clients and saves them to a list to be used in future operations. This scan can be stopped with [stopscan](https://github.com/justcallmekoko/ESP32Marauder/wiki/stopscan). The [list](https://github.com/justcallmekoko/ESP32Marauder/wiki/list) of scanned stations can be shown with list and cleared with [clearlist](https://github.com/justcallmekoko/ESP32Marauder/wiki/clearlist).


Before `scansta` can detect stations in range, you must scan for access points with [`scanap`](../scanap). During `scansta`, Marauder will only save scanned stations to the station list if they are associated with access points that are already part of the access point list generated from [`scanap`](../scanap).

## Usage
`scansta`