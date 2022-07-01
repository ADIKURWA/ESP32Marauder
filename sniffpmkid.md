# sniffpmkid
Sniffs and displays captured pmkid/eapol frames sent during WiFi authentication sessions. Unlike other sniffing functions, the raw frame data is displayed on screen to be copied and saved elsewhere. This scan can be stopped with [`stopscan`](stopscan). `sniffpmkid` will **NOT** automatically cycle through channels while sniffing. In order to change to a new channel while sniffing, use [`channel`](channel). For more information on PMKID and 4-way handshakes, see [4-Way Handshake](https://www.wifi-professionals.com/2019/01/4-way-handshake)

## Usage
```sniffpmkid [-c <channel>] [-d]```

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-c <channel>` | Optional | Specify the channel to start sniffing on |
| `-d` | Optional | Send deauthentication frames to trigger handshakes |