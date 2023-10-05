# Wardrive
<a href="https://wigle.net">
<img border="0" src="https://wigle.net/bi/rP_pTNT9Hiwp+cB9UszVQg.png">
</a>  

This function allows users to continuously scan for WiFi networks. Once a network is detected, the current position from the attached GPS module along with the network information is logged and saved to a file with "wardrive" prefix to SD card. To exit the scan, simply tap the screen. Because of the method of scanning, it may take multiple taps to exit. **This function requires the [GPS Modification](gps-modification).**

Station Wardrive performs a scan for WiFi client devices. These devices are detected through probe requests. They're location data as well as the scan information is saved to a log file. The scanned addresses are not cached which means they will continue to be scanned, displayed, and logged.

During the scan, network information is only saved to the log file as long as the GPS has a valid fix which can change at any point during the scan depending on location, weather, and antenna.

The following information is displayed on screen while sniffing:  
- Source ESSID/BSSID
- Latitude and Longitude (if valid fix)
- "No Fix" (if no valid fix)

## Menu Path
`WiFi`>`Sniffers`>`Wardrive`

## CLI
This function is available for use via the [Marauder CLI](cli). The following documentation describes command usage. The wardrive function can be stopped with [`stopscan`](stopscan).

### Usage
`wardrive [-s]`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-s` | Optional | Wardrive for stations instead of access points |

## Wardrive Log Output
Logs are saved to the onboard SD card or to the Flipper SD card (if you have the serial firmware installed) with the prefix "wardrive_". These files can be uploaded to [wigle.net](https://www.wigle.net) and will count towards your personal stats.

## Thanks
Huge thanks to [JosephHewitt](https://github.com/JosephHewitt/) for his [Wardriver](https://github.com/JosephHewitt/wardriver_rev3/tree/main) project. Much of his code was repurposed to satisfy the need for a wardriving function in the Marauder firmware.