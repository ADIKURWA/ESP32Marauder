# Bluetooth Wardrive
This function allows users to detect bluetooth devices and save their information along with location data to a log file. This function requires the [GPS Modification](gps-modification). Devices are only displayed and logged on first detection. To exit the scan session, tap anywhere on the screen.

During a continuous bluetooth wardrive, the function is the same except device information is not cached and therefore will continue to display and log repeat detections.

The following information is displayed on screen while sniffing:

  - Source MAC
  - Latitude and Longitude (if valid fix)
  - "No Fix" (if no valid fix)

## Menu Path
`Bluetooth`>`Sniffers`>`Bluetooth Wardrive`

## CLI
This function is available for use via the [Marauder CLI](https://github.com/justcallmekoko/ESP32Marauder/wiki/cli). The following documentation describes command usage. The bluetooth wardrive function can be stopped with [stopscan](https://github.com/justcallmekoko/ESP32Marauder/wiki/stopscan).

### Usage
`btwardrive [-c]`

### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-c` | Optional | Do not filter on repeat device detection |

## Bluetooth Wardrive Log Output
Logs are saved to the onboard SD card or to the Flipper SD card (if you have the serial firmware installed) with the prefix "bt_wardrive_".