# Marauder Versions
There are several different versions of Marauder I have developed. Each Marauder has its own range of capabilities, some better than others. The following list describes each official version of the ESP32 Marauder.  

## ESP32 Marauder
This is the original ESP32 Marauder. The first Marauder which was available for purchase on Tindie. This Marauder design has undergone several changes including:  
- Resistor network implementation
- IP5306 to IP5306 I2C transition
- ESP32 WROOM IPEX
- SD Card implementation

*Picture needed here*

The original Marauder only features a single ESP32 WROOM chip, a two piece 3D printed enclosure, Micro USB Charging and programming, and rechargeable LiPo battery. This is one of two versions which has been sold on Tindie as of 27APR2021. **This version does not include BadUSB or Deauthentication capabilities**.  

## ESP32 Marauder v6
Counter to what the name implies, this is the second official iteration of the ESP32 Marauder. As of 27APR2021, I have only made one release of 10 units. The main differences between this iteration and its predecessor is its use of a push-in push-out micro SD card slot, single PCB design with the TFT fixed directly to the PCB, 18650 Battery holder, single piece 3D printed back plate, and a single WS2812b RGB LED on the front of the tool. Aside from those aspects, the overall functionality of this version remains the same as the previous.  

*Picture needed here*

## ESP32 Marauder Centauri
After considering the input from the community, I decided to design a Marauder which features a physical keyboard situated beneath a landscape oriented TFT screen. The Marauder Centauri was named after a binary star system because it includes two separate WiFi chips (ESP32 and ESP8266).  

*Picture needed here*

Like the ESP32 Marauder v6, the Centauri includes an 18650 battery holder and a TFT Screen soldered directly to the main PCB. The back plate is actually a full single piece enclosure. The charging circuit remains the same, but the micro USB port has been replaced with USB-C. The ESP32 serves as a Serial-to-serial proxy to relay information between a USB connected PC and the ESP8266. For more information, see [ESP8266 Update](esp8266-update). The physical keyboard is driven by an ATmega328p which communicates all keypresses to the ESP32 over I2C. In addition to a full keyboard, the keyboard PCB includes a 5-way tactile switch for interface navigation should the user decide to forgo the use of the touch screen.

## ESP32 Marauder 7
As of 27APR2021, this is the latest version of the ESP32 Marauder. The PCB footprint and enclosure design is the same as the original ESP32 Marauder. This was done on purpose to give it somewhat of a [sleeper](https://www.urbandictionary.com/define.php?term=sleeper) status. The ESP32 Marauder 7 features an ESP32 WROOM, ESP8266, and an ATmega32u4, giving it the ability to execute WiFi and Bluetooth analysis operations, Deauthentication attacks, and keystroke injection attacks. For more information on these analysis and attack methodologies, see [WiFi Sniffers](wifi-sniffers), [WiFi Attacks](wifi-attacks), [Bluetooth Sniffers](bluetooth-sniffers), and [BadUSB](badusb).  

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_1838.JPG?raw=true" width="300">
</p> 

Like the Marauder Centauri, the ESP32 Marauder 7 uses a USB-C port for USB communication and charging. The ESP32 still functions as a serial data proxy between the ESP8266 and the PC. Because of the ATmega32u4's native USB support, it is able to interface directly with a connected PC. The ATmega32u4 and CH340C (USB to UART convert for ESP32) are able to communicate with a connected PC through the single USB-C port. This is accomplished by using a USB Hub IC. For more information on these ICs and their connections, see [IC Connections](ic-connections).

For user awareness and troubleshooting, status LEDs are used to represent the serial communication between all ICs present on the Marauder 7 PCB.