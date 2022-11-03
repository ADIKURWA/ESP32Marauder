# attack
Transmit WiFi frames with specific target or broadcast

## Usage
`attack -t <beacon [-l/-r/-a]/deauth [-s <src mac>] [-d <dst mac>]/probe/rickroll>`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-t <type>` | Required | Specify the attack type: [`beacon`](#beacon), [`deauth`](#deauth), [`probe`](#probe), [`rickroll`](#rickroll)|
| `-l/-r/-a` | Required (for [`beacon`](#beacon)) | Specify "list", "random", or "ap" attack for beacon spam |
| `-s <src_mac>` | Optional | Specify a source MAC address for deauthentication attack |
| `-d <dst_mac>` | Optional | Specify a destination MAC address for deauthentication attack |

## beacon
Before executing a beacon spam `list` attack on the ESP32 Marauder, you must build a list of SSIDs using [`ssid`](ssid). Once you have a list of SSIDs that can be used for a beacon spam attack, the attack can be executed and all SSIDs in your list will be transmitted as beacons. The attack can be ended with [`stopscan`](stopscan).
#### Beacon Spam AP
Beacon Spam AP spams beacon frames that copy a known access point scanned by [`scanap`](scanap). Before you can execute this attack, you must use [`scanap`](scanap) to build a target list and [`select`](select) to pick specific APs to copy.

#### Examples
Spam your list of generated SSIDs: `attack -t beacon -l`  
Spam random SSIDs: `attack -t beacon -r`  
Create fake copies of an AP: `attack -t beacon -a`  

## deauth
Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target unless you use the command argument, `-s` as shown above. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a deauth flood can be executed. The attack can be ended with [`stopscan`](stopscan). For more information on deauthentication attacks, see [Wi-Fi deauthentication attack](https://en.wikipedia.org/wiki/Wi-Fi_deauthentication_attack).

#### Examples
Target selected APs: `attack -t deauth`  
Manually specify Source MAC: `attack -t deauth -s AA:BB:CC:DD:EE:FF`  
Manually specify source and destination: `attack -t deauth -s AA:BB:CC:DD:EE:FF -d AA:BB:CC:DD:EE:FF`  

## probe
Before executing probe request flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a probe request flood can be executed. The attack can be ended with [`stopscan`](stopscan). For more information on probe request attacks, see [Probe Requests](https://blog.spacehuhn.com/probe-request/).

#### Examples
Run standard probe request attack: `attack -t probe`  

## rickroll
You'll just have to find out