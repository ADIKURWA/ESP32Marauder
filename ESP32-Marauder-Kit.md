# ESP32 Marauder Kit
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3491%20-%20Copy.jpg?raw=true" width="500">
</p>

The ESP32 Marauder Kit is a bundle of hardware components that allow a user to assemble a fully functional ESP32 Marauder. All that is required from the user is that they must provide their own [Adafruit Huzzah32](https://www.adafruit.com/product/3405) flashed with the ESP32 Marauder firmware, and a 3.7V LiPo battery compatible with the Huzzah32. 

# Table of Contents
- [Kit Contents](#kit-contents)
- [Assembling Hardware](#assembling-hardware)
- [Firmware Install Options (Pick One)](#firmware-install-options-pick-one)
  - [Installing Firmware Over The Air (OTA) (Option 1)(easy)](#installing-firmware-over-the-air-ota-option-1easy)
  - [Building and Installing Firmware from source (Option 2)(not easy)](#building-and-installing-firmware-from-source-option-2not-easy)
- [Using Your ESP32 Marauder Kit](#using-your-esp32-marauder-kit)

## Kit Contents
#### What is included
- 1x ESP32 Marauder Kit PCB
- 1x 3D printed enclosure w/ threaded brass inserts
- 4x M2.5 x 9mm hex screws
- 1x Documentation slip with QR code

#### What is required but not included
- 1x [3.7v LiPo battery with JST connector](https://www.adafruit.com/?q=3.7v+lithium&sort=BestMatch)
- 1x [Adafruit Huzzah32](https://www.adafruit.com/product/3405)

## Assembling Hardware
1. Solder the male header pins included with your Adafruit Huzzah32 to the Huzzah32 board
    - *supporting image here*
2. Connect the Huzzah32 to the ESP32 Marauder Kit PCB
    - *supporting image here*
3. Connect your 3.7V LiPo battery to the JST connector of the Huzzah32
    - Ensure the power switch of the ESP32 Marauder Kit PCB is in the `off` position
    - If you need to remove the battery, be careful not to rip the wires from the JST housing. The JST connector is tight
4. Using some sort of adhesive such as double sided tape or glue, fix the 3.7V LiPo battery to the inside of the Marauder enclosure
    - *supporting image here*
5. Using the 4 included M2.5 x 5mm screws, screw the ESP32 Marauder PCB to the enclosure so that the TFT Touch screen faces outward
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3484%20-%20Copy.jpg?raw=true" height="400">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3485%20-%20Copy.jpg?raw=true" height="400">
</p>

## Firmware Install Options (Pick One)
You have two options for installing firmware. If you want to hit the ground running as fast as possible with minimal effort, I recommend Option 1. You will also have Option 1 available in future firmware updates (see [Update Firmware](update-firmware)). If you want to get to know the source code and the build process, try Option 2. If Option 2 fails, try Option 1.

### Installing Firmware Over The Air (OTA) (Option 1)(easy)
To install a pre-compiled binary of the ESP32 Marauder firmware, pick any of the options under [Update Firmware](update-firmware)

### Building and Installing Firmware from source (Option 2)(not easy)
To build the ESP32 Marauder firmware from source and install it on the Adafruit Huzzah32, follow the instructions under [Installing Firmware From Source](installing-firmware-from-source).

## Using Your ESP32 Marauder Kit
Now that you have assembled and programmed your Adafruit Huzzah32, you should have a fully functional ESP32 Marauder. To start getting familiar with its capabilities, read through the [Applications](applications).