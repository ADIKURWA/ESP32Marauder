# attack
Transmit WiFi frames with specific target or broadcast

## Usage
`attack -t <type>`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-t` | Required | Specify the attack type: [`beacon`](#beacon), [`deauth`](#deauth), [`probe`](#probe)|

## beacon

## deauth
The ESP32 is capable of transmitting specially crafted WiFi packets. Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a deauth flood can be executed. The attack can be ended with [`stopscan`](stopscan).

## probe