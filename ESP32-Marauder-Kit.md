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

### What is required but not included
- 1x 3.7v LiPo battery with JST connector
- 1x Adafruit Huzzah32

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
The original ESP32 Marauder firmware uses many libraries and a few IDF modifications. To avoid having to install and configure all of these libraries, this options allows the user to install a very basic firmware to the ESP32 Marauder. This firmware will not involve any additional libraries or configurations and it will allow the user to install the precompiled Marauder binary via a web browser.

1. Follow the instructions under [Arduino IDE Setup](arduino-ide-setup)
2. Open the Arduino IDE
3. Plug your ESP32 Marauder Kit into a USB port using a micro USB data cable and select the COM port under `Tools`>`Port`
4. Select the appropriate ESP32 module under `Tools`>`Boards`
    - If you are using the ESP32 Marauder Kit: `Adafruit ESP32 Feather`
    - If you do not see this board option, ensure your Arduino IDE is on the latest version
5. For partition scheme, select `Minimal SPIFFS (Large APPS with OTA)`
6. Copy the ESP32 Marauder OTA Upload firmware source from [here](https://raw.githubusercontent.com/justcallmekoko/ESP32Marauder/master/MarauderOTA/MarauderOTA.ino) into your Arduino IDE window
7. Click the Upload button in the top left corner of the Arduino IDE and let the code compile and upload to the ESP32 Marauder
8. Download the [latest release](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) of the ESP32 Marauder firmware
    - The file you want will have `_kit` at the end of its name
9. With the ESP32 Marauder Kit powered on, Connect to the ESP32 Marauder OTA WiFi network
    - Network ESSID: `MarauderOTA`
    - Network Password: `justcallmekoko`
10. Open your web browser application
11. Navigate to http://192.168.4.1
12. Login using the provided credentials
    - Username: `admin`
    - Password: `admin`
13. Once you are logged in, refresh the web page
14. Browse for the firmware file you downloaded
15. Click the `Update` button
    - The ESP32 Marauder will automatically reboot once the update process is complete

### Building and Installing Firmware from source (Option 2)(not easy)
To build the ESP32 Marauder firmware from source and install it on the Adafruit Huzzah32, follow the instructions under [Installing Firmware](installing-firmware).

## Using Your ESP32 Marauder Kit
Now that you have assembled and programmed your Adafruit Huzzah32, you should have a fully functional ESP32 Marauder. To start getting familiar with its capabilities, read through the [Applications](applications).