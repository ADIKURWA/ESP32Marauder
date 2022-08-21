# Flipper Zero WiFi Dev Board with Marauder

[![Build and Push](https://github.com/justcallmekoko/ESP32Marauder/actions/workflows/build_push.yml/badge.svg)](https://github.com/justcallmekoko/ESP32Marauder/actions/workflows/build_push.yml)
### Summary
The Flipper Zero has the option to attach different peripherals to it's GPIO headers. One such option is the [ESP32-S2 Development Board](https://shop.flipperzero.one/products/wifi-devboard) which provides the Flipper Zero with the hardware required for WiFi capabilities. The Marauder firmware can be installed on the ESP32-S2 either via prebuilt firmware binary uploaded [over-the-air(OTA)](installing-firmware-via-ota) or via [configured source build and upload](installing-firmware-from-source). For either process, it will be assumed the connection between your PC and your WiFi dev board is "direct" i.e. you are not using the Flipper Zero USB-to-UART bridge. Once the install is complete however, you will be required to use the Flipper Zero USB-to-UART bridge.

#### Firmware install options
| Blue pill | Red Pill |
| --------- | -------- |
| Really easy. Nothing to change, but you don't get any customization (which is fine). | This pill is the size of a large pumpkin and it goes in your ass. Install libraries, build from source, know everything |
| [Marauder OTA](installing-firmware-via-ota) | [Build from source](installing-firmware-from-source)

Once you install the Marauder firmware on the WiFi dev board, you can connect the dev board to the Flipper Zero GPIO header and connect the flipper to your PC or Android phone via USB cable.  
On the Flipper Zero, navigate to `GPIO`>`USB-UART Bridge`. I keep my Bridge configured to use USB channel 0

## Having Issues?
If you are having issues with your Marauder installation either with the install process or with the firmware usage, be sure to check if your issue has already been solved in [FAQ](../faq). If not, feel free to join my [Discord](https://discord.gg/invite/w5JmasxvKA) to request help from the community or submit an [issue](https://github.com/justcallmekoko/ESP32Marauder/issues)

### Tethered Usage
Marauder can be used via its [command-line interface](cli) supplemented by the Flipper Zero USB-to-UART bridge and a PC/Laptop. The goal is to eventually get the Flipper Zero to offer a bluetooth connection to facilitate a Serial-over-Bluetooth bridge to the WiFi Dev Board so everything can be done over mobile phone.

### Untethered Usage
If you would like to use the Flipper Zero and it's WiFi dev board flashed with Marauder as a standalone unit without a PC or mobile phone attached, install [flipperzero-firmware-wPlugins](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/releases/latest) by [RogueMaster](https://github.com/RogueMaster) on your Flipper Zero. It features an interface directly available on the Flipper Zero menu which allows full control of the Marauder firmware running on the dev board.

### SD Card Modification
A MicroSD card can be attached to the Flipper Zero WiFi Dev Board SPI via a [MicroSD Breakout](https://www.sparkfun.com/products/544). Attaching a microSD card to the Flipper Zero WiFi Dev Board will allow the Marauder firmware to save captured WiFi traffic to storage in the form of PCAP files to be exported for analysis later. Refer to the following table for the required solder connections

| MicroSD Breakout | Flipper Zero WiFi Dev Board |
| ---------------- | --------------------------- |
| VCC              | 3V3                         |
| GND              | GND                         |
| DI (MOSI)        | IO35                        |
| DO (MISO)        | IO37                        |
| SCK              | IO36                        |
| CS               | IO10                        |

Once all of the solder connections have been made, a piece of double-sided tape can be used to fix the MicroSD Breakout Board to the back of the WiFi Development Board.
<p align="left"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5876%20-%20Copy.jpg?raw=true" width="500"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5877%20-%20Copy.jpg?raw=true" width="500"></p><br>
<p align="left"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5879%20-%20Copy.jpg?raw=true" width="500"></p>

## YouTube Video
[![Tutorial](https://img.youtube.com/vi/_YLTpNo5xa0/0.jpg)](https://www.youtube.com/watch?v=_YLTpNo5xa0)