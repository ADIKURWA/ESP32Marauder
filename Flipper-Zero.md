# Flipper Zero WiFi Dev Board with Marauder

### Summary
The Flipper Zero has the option to attach different peripherals to it's GPIO headers. One such option is the [ESP32-S2 Development Board](https://shop.flipperzero.one/products/wifi-devboard) which provides the Flipper Zero with the hardware required for WiFi capabilities. The Marauder firmware can be installed on the ESP32-S2 either via prebuilt firmware binary uploaded [over-the-air(OTA)](installing-firmware-via-ota) or via [configured source build and upload](installing-firmware-from-source). For either process, it will be assumed the connection between your PC and your WiFi dev board is "direct" i.e. you are not using the Flipper Zero USB-to-UART bridge. Once the install is complete however, you will be required to use the Flipper Zero USB-to-UART bridge.

#### Firmware install options
| Blue pill | Red Pill |
| --------- | -------- |
| Really easy. Nothing to change, but you don't get any customization (which is fine). | This pill is the size of a large pumpkin and it goes in your ass. Install libraries, build from source, know everything |
| [Marauder OTA](installing-firmware-via-ota) | [Build from source](installing-firmware-from-source)

### Usage
Marauder can be used via its [command-line interface](cli) supplemented by the Flipper Zero USB-to-UART bridge and a PC/Laptop. The goal is to eventually get the Flipper Zero to offer a bluetooth connection to facilitate a Serial-over-Bluetooth bridge to the WiFi Dev Board so everything can be done over mobile phone.