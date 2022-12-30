# Flipper Zero WiFi Dev Board with Marauder

[![Build and Push](https://github.com/justcallmekoko/ESP32Marauder/actions/workflows/build_push.yml/badge.svg)](https://github.com/justcallmekoko/ESP32Marauder/actions/workflows/build_push.yml)

If at any moment you need further guidance, consider joining the discord server.  
<a href="https://discord.com/servers/willstunforfood-776211399918878760"><img src="https://discordapp.com/api/guilds/776211399918878760/widget.png?style=banner4" alt="JustCallMeKoko Discord"></a>

## Table of Consonants
- [Summary](#summary)
- [WiFi Dev Board Enclosure](#wifi-dev-board-enclosure)
- [Firmware Install Options](#firmware-install-options)
  - [Video Guide](#video-guide)
- [Don't have a dev board?](#dont-have-a-dev-board)
- [Having Issues?](#having-issues)
- [Tethered Usage](#tethered-usage)
- [Untethered Usage](#untethered-usage)
- [SD Card Modification](#sd-card-modification)
- [Patreon](#patreon)
- [YouTube Video](#youtube-video)
- [More Videos](#more-videos)
- [Next Steps](#next-steps)

### Summary
The Flipper Zero has the option to attach different peripherals to it's GPIO headers. One such option is the [ESP32-S2 Development Board](https://shop.flipperzero.one/products/wifi-devboard) which provides the Flipper Zero with the hardware required for WiFi capabilities. The Marauder firmware can be installed on the ESP32-S2 either via prebuilt firmware binary uploaded [over-the-air(OTA)](installing-firmware-via-ota) or via [configured source build and upload](installing-firmware-from-source). For either process, it will be assumed the connection between your PC and your WiFi dev board is "direct" i.e. you are not using the Flipper Zero USB-to-UART bridge. Once the install is complete however, you will be required to use the Flipper Zero USB-to-UART bridge.   

It is recommended to use the **Flasher Script** option if you choose "Blue Pill" as this is the quickest and most direct method for installing the Marauder firmware on your WiFi Dev Board

### [WiFi Dev Board Enclosure](https://www.tindie.com/products/justcallmekoko/flipper-zero-wifi-dev-board-enclosure/)
If you do not currently own a 3D printer and would like to purchase an enclosure for your WiFi Dev Board, I am currently selling them on Tindie with multiple color and material options. If you are interested, check out the shop [here](https://www.tindie.com/products/justcallmekoko/flipper-zero-wifi-dev-board-enclosure/).
<p align="left"><img alt="Enclosure" src="https://cdn.tindiemedia.com/images/resize/8NU10HwLlY6YAxBMm5zmX4wplCM=/p/fit-in/653x435/filters:fill(fff)/i/663561/products/2022-06-22T17%3A49%3A07.471Z-IMG_2245.JPG?1655894975" width="300"><img alt="Enclosure" src="https://cdn.tindiemedia.com/images/resize/nlp5ZR3FJufeel8-LY3qtmIj9Ps=/p/fit-in/1370x912/filters:fill(fff)/i/663561/products/2022-06-22T17%3A49%3A07.471Z-IMG_2242.JPG?1655894975" width="300"></p><br>
<p align="left"><img alt="Enclosure" src="https://cdn.tindiemedia.com/images/resize/JFiK85Igb1EH4Sw9ACKfrHPCP8I=/p/fit-in/1370x912/filters:fill(fff)/i/663561/products/2022-08-23T17%3A05%3A36.894Z-IMG_5955%20-%20Copy.jpg?1661249267" width="500"></p>

### Firmware install options
| Blue pill | Red Pill |
| --------- | -------- |
| Really easy. Nothing to change, but you don't get any customization (which is fine). | This pill is the size of a large pumpkin and it goes in your ass. Install libraries, build from source, know everything |
| [FZ Marauder Flasher](https://github.com/UberGuidoZ/Flipper/tree/main/Wifi_DevBoard/FZ_Marauder_Flasher), [FZEasyMarauderFlash](https://github.com/SkeletonMan03/FZEasyMarauderFlash), or [Marauder OTA](installing-firmware-via-ota) | [Build from source](installing-firmware-from-source)

Once you have installed the firmware, be sure to check [what to do next](#next-steps).

#### Video Guide
This video by [Lab 401](https://www.youtube.com/c/Lab401) will provide instructions for using the flasher script. This is the quickest way to get Marauder running on your device  
[![Tutorial](https://img.youtube.com/vi/um_acrDaBK4/0.jpg)](https://www.youtube.com/watch?v=um_acrDaBK4)


Once you install the Marauder firmware on the WiFi dev board, you can connect the dev board to the Flipper Zero GPIO header and connect the flipper to your PC or Android phone via USB cable.  
On the Flipper Zero, navigate to `GPIO`>`USB-UART Bridge`. I keep my Bridge configured to use USB channel 0

### Don't have a dev board?
If you don't have a dev board, you can learn how to make one here...  
[![Tutorial](https://i3.ytimg.com/vi/uc5_hVmJ-3Y/maxresdefault.jpg)](https://www.youtube.com/watch?v=uc5_hVmJ-3Y)

## Having Issues?
If you are having issues with your Marauder installation either with the install process or with the firmware usage, be sure to check if your issue has already been solved in [FAQ](../faq). If not, feel free to join my [Discord](https://discord.gg/invite/w5JmasxvKA) to request help from the community or submit an [issue](https://github.com/justcallmekoko/ESP32Marauder/issues)

### Tethered Usage
Marauder can be used via its [command-line interface](cli) supplemented by the Flipper Zero USB-to-UART bridge and a PC/Laptop. The goal is to eventually get the Flipper Zero to offer a bluetooth connection to facilitate a Serial-over-Bluetooth bridge to the WiFi Dev Board so everything can be done over mobile phone.  
For tethered use, follow these steps...
1. Connect your dev board to your flipper zero and power it on
2. Connect your flipper zero to your PC/Mobile phone via USB-C
3. On your flipper, open the USB-UART Bridge via the GPIO menu
4. Configure the bridge to use USB channel 0 with baud 115200
5. On your PC or mobile device, open a serial connection to the Flipper Zero with baud 115200
    - Be sure to check what COM port your flipper zero is on so you know what to connect to

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
<p align="left"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5876%20-%20Copy.jpg?raw=true" width="300"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5877%20-%20Copy.jpg?raw=true" width="300"></p><br>
<p align="left"><img alt="Marauder logo" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_5879%20-%20Copy.jpg?raw=true" width="500"></p>

## Patreon
If you are looking to support me and my pursuit of shitty projects, consider heading over to my [Patreon](https://www.patreon.com/justcallmekoko). It aint much and it's not very big around, but it'll get the job done.

## YouTube Video
The following video describes and demonstrates the installation and usage of the Marauder firmware on the Flipper Zero WiFi Dev Board.  
[![Tutorial](https://img.youtube.com/vi/_YLTpNo5xa0/0.jpg)](https://www.youtube.com/watch?v=_YLTpNo5xa0)

## More videos
[![More Videos](https://img.youtube.com/vi/1ftcESq-pNY/0.jpg)](https://www.youtube.com/watch?v=1ftcESq-pNY)
[![More Videos](https://img.youtube.com/vi/nEBZ4VeTj7I/0.jpg)](https://www.youtube.com/watch?v=nEBZ4VeTj7I)
[![More Videos](https://img.youtube.com/vi/Deh5NBr0e_A/0.jpg)](https://www.youtube.com/watch?v=Deh5NBr0e_A)

## Next Steps
If you're trying to figure out what to do now that you have Marauder installed on your Flipper Zero, consider reading [Commandline](cli) for how to use the Marauder command line interface, and [Workflow Examples](workflow-examples) to understand how to use some of the commands in a practical way.