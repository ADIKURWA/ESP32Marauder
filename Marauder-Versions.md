# Marauder Versions
There are several different versions of Marauder I have developed. Each Marauder has its own range of capabilities, some better than others. The following list describes each official version of the ESP32 Marauder.  

## Big Table of Features and stuff
|                | v4 (OG)            | v6                 | v7                 | Kit                | Mini               | Flipper            |
| -------------- | ------------------ | ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| Display        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                |
| Touch          | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| Tactile Switch | :x:                | :x:                | :x:                | :x:                | :heavy_check_mark: | :x:                |
| SD Card        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:(with mod) |
| Battery        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:(with flipper) |
| WiFi           | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Bluetooth      | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                |
| Command Line   | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Packet Monitor | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| Onscreen Keybd | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| PMKID Capture  | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Deauth         | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Raw Capture    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| AP Select      | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Manual SSID    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:(CLI Only) | :heavy_check_mark:(CLI Only) |
| OTA Update     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| SD Update      | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark:(with mod) |
| Status LED     | :x:                | :heavy_check_mark: | :x:                | :x:                | :x:                | :heavy_check_mark: |
| HID attacks    | :x:                | :x:                | :heavy_check_mark: | :x:                | :x:                | :x:                |
| ESP8266 co-mcu | :x:                | :x:                | :heavy_check_mark: | :x:                | :x:                | :x:                |

## ESP32 Marauder v4 (OG)
This is the original ESP32 Marauder. The first Marauder which was available for purchase on Tindie. This is the most fully featured, widely known, and widely available version of the Marauder.

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_0124.JPG?raw=true" width="500">
</p>

The original Marauder only features a single ESP32 WROOM chip, a two piece 3D printed enclosure, Micro USB Charging and programming, and rechargeable LiPo battery. This is one of two versions which has been sold on Tindie as of 27APR2021.

## ESP32 Marauder v6
Counter to what the name implies, this is the second official iteration of the ESP32 Marauder. The main differences between this iteration and its predecessor is its use of a push-in push-out micro SD card slot, single PCB design with the TFT fixed directly to the PCB, 18650 Battery holder, single piece 3D printed back plate, and a single WS2812b RGB LED on the front of the tool. Aside from those aspects, the overall functionality of this version remains the same as the previous.  

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_0426.JPG?raw=true" width="500">
</p>

## ESP32 Marauder v7
As of 27APR2021, this is the latest version of the ESP32 Marauder. The PCB footprint and enclosure design is the same as the original ESP32 Marauder. This was done on purpose to give it somewhat of a [sleeper](https://www.urbandictionary.com/define.php?term=sleeper) status. The ESP32 Marauder v7 features an ESP32 WROOM, ESP8266, and an ATmega32u4, giving it the ability to execute WiFi and Bluetooth analysis operations, Deauthentication attacks, and keystroke injection attacks. For more information on these analysis and attack methodologies, see [WiFi Sniffers](wifi-sniffers), [WiFi Attacks](wifi-attacks), [Bluetooth Sniffers](bluetooth-sniffers), and [BadUSB](badusb).  

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_1838.JPG?raw=true" width="500">
</p> 

The ESP32 Marauder v7 uses a USB-C port for USB communication and charging. The ESP32 still functions as a serial data proxy between the ESP8266 and the PC. Because of the ATmega32u4's native USB support, it is able to interface directly with a connected PC. The ATmega32u4 and CH340C (USB to UART convert for ESP32) are able to communicate with a connected PC through the single USB-C port. This is accomplished by using a USB Hub IC. For more information on these ICs and their connections, see [IC Connections](ic-connections).

For user awareness and troubleshooting, status LEDs are used to represent the serial communication between all ICs present on the Marauder 7 PCB.
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_1849.JPG?raw=true" width="500">
</p>

## ESP32 Marauder Kit
It's a kit
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3491%20-%20Copy.jpg?raw=true" width="500">
</p>