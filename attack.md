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
| `-c` | Optional | Use only selected stations from the [Station List](list) |

## beacon
Before executing a beacon spam `list` attack on the ESP32 Marauder, you must build a list of SSIDs using [`ssid`](ssid). Once you have a list of SSIDs that can be used for a beacon spam attack, the attack can be executed and all SSIDs in your list will be transmitted as beacons. The attack can be ended with [`stopscan`](stopscan).
#### Beacon Spam AP
Beacon Spam AP spams beacon frames that copy a known access point scanned by [`scanap`](scanap). Before you can execute this attack, you must use [`scanap`](scanap) to build a target list and [`select`](select) to pick specific APs to copy.

#### Examples
Spam your list of generated SSIDs: `attack -t beacon -l`  
Spam random SSIDs: `attack -t beacon -r`  
Create fake copies of an AP: `attack -t beacon -a`  

## deauth
There are 3 different methods to execute a deauthentication attack with the Marauder. These methods are described below.  
**For more information on how to properly execute these deauthentication attacks, please see [Deauthentication Attack Workflow](deauthentication-attack-workflow) and check the examples below.**

#### Method 1 (Flood)
In a deauthentication flood attack, a target access point is specified as the source address of each deauthentication frame sent. The destination address of these frames is set to broadcast. The intention is for **all** stations connected to the target access point to be removed from that network.  
Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a deauth flood can be executed.

#### Method 2 (Targeted)
In a targeted deauthentication attack, each deauthentication frame is tailored to a specific target station/client associated with a target access point. The intention is for only specifically targeted stations to be deauthenticated from the targeted access points rather than all stations like in a flood.
Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and stations. You must also select which access points and stations to target. See [scanap](scanap), [scansta](scansta) and [select](select) for more details on how to build a target list.

#### Method 3 (Manual)
In a manual deauthentication attack, the source and destination address of the deauthentication frames sent are hand jammed by the end user. This is valuable for benign testing purposes or to attack an access points or station not found during scans. Unlike the previous two methods, no scans or lists are required to execute this attack. The user only need specify the source address and destination address with the `-s` and `-d` switch options respectively.

All 3 deauthentication attack methods can be ended with [`stopscan`](stopscan). For more information on deauthentication attacks, see [Wi-Fi deauthentication attack](https://en.wikipedia.org/wiki/Wi-Fi_deauthentication_attack).

#### Examples
Target selected APs: `attack -t deauth`  
Target selected APs and Stations: `attack -t deauth -c`  
Manually specify Source MAC: `attack -t deauth -s AA:BB:CC:DD:EE:FF`  
Manually specify source and destination: `attack -t deauth -s AA:BB:CC:DD:EE:FF -d AA:BB:CC:DD:EE:FF`  

**For more information on how to properly execute these deauthentication attacks, please see [Deauthentication Attack Workflow](https://github.com/justcallmekoko/ESP32Marauder/wiki/deauthentication-attack-workflow).**

## probe
Before executing probe request flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [scanap](scanap) and [select](select) for more details on how to build a target list.

Once a proper target list has been built, a probe request flood can be executed. The attack can be ended with [`stopscan`](stopscan). For more information on probe request attacks, see [Probe Requests](https://blog.spacehuhn.com/probe-request/).

#### Examples
Run standard probe request attack: `attack -t probe`  

## rickroll
You'll just have to find out