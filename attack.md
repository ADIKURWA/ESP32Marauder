# attack
Transmit WiFi frames with specific target or broadcast

## Usage
`attack -t <type>`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-t` | Required | Specify the attack type: [`beacon`](#beacon), [`deauth`](#deauth), [`probe`](#probe)|
| `-l/-r` | Required (for [`beacon`](#beacon)) | Specify "list" attack or "random" attack for beacon spam |

## beacon
Before executing a beacon spam attack on the ESP32 Marauder, you must build a list of SSIDs using [`ssid`](ssid). Once you have a list of SSIDs that can be used for a beacon spam attack, the attack can be executed and all SSIDs in your list will be transmitted as beacons. The attack can be ended with [`stopscan`](stopscan).

## deauth
Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a deauth flood can be executed. The attack can be ended with [`stopscan`](stopscan). For more information on deauthentication attacks, see [Wi-Fi deauthentication attack](https://en.wikipedia.org/wiki/Wi-Fi_deauthentication_attack).

## probe
Before executing probe request flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a probe request flood can be executed. The attack can be ended with [`stopscan`](stopscan). For more information on probe request attacks, see [Probe Requests](https://blog.spacehuhn.com/probe-request/).