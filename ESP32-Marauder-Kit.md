# ESP32 Marauder Kit
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3491%20-%20Copy.jpg?raw=true" width="500">
</p>

The ESP32 Marauder Kit is a bundle of hardware components that allow a user to assemble a fully functional ESP32 Marauder. All that is required from the user is that they must provide their own [Adafruit Huzzah32](https://www.adafruit.com/product/3405) flashed with the ESP32 Marauder firmware, and a 3.7V LiPo battery compatible with the Huzzah32. 

# Table of Contents
- [Firmware Install Options (Pick One)](#firmware-install-options-pick-one)
  - [Installing Firmware Over The Air (OTA) (Option 1)(easy)](#installing-firmware-over-the-air-ota-option-1easy)
  - [Building and Installing Firmware from source (Option 2)(not easy)](#building-and-installing-firmware-from-source-option-2not-easy)
- [Assembling Hardware](#assembling-hardware)
- [Using Your ESP32 Marauder Kit](#using-your-esp32-marauder-kit)

## Firmware Install Options (Pick One)
You have two options for installing firmware. If you want to hit the ground running as fast as possible with minimal effort, I recommend Option 1. If you want to get to know the source code and the build process, try Option 2. If Option 2 fails, try Option 1.

### Installing Firmware Over The Air (OTA) (Option 1)(easy)
*to-do*
- Follow the instructions under [Arduino IDE Setup](arduino-ide-setup)
- Open the Arduino IDE
- Plug your ESP32 Marauder Kit into a USB port and select the COM port under `Tools`>`Port`
- Select the appropriate ESP32 module under `Tools`>`Boards`
    - If you are using the ESP32 Marauder Kit: `Adafruit ESP32 Feather`
- For partition scheme, select `Minimal SPIFFS (Large APPS with OTA)`
- Copy the ESP32 Marauder OTA Upload firmware source from *(to-do)*[here](esp32-marauder-kit) into your Arduino IDE window
- Click the Upload button in the top left corner of the Arduino IDE and let the code compile and upload to the ESP32 Marauder
- Download the [latest release](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) of the ESP32 Marauder firmware
- Connect to the ESP32 Marauder OTA WiFi network
    - Network ESSID: `MarauderOTA`
    - Network Password: `justcallmekoko`
- Open your web browser application
- Navigate to http://192.168.4.1
- Login using the provided credentials
    - Username: `admin`
    - Password: `admin`
- Once you are logged in, refresh the web page
- Browse for the firmware file you downloaded
- Click the `Update` button
    - The ESP32 Marauder will automatically reboot once the update process is complete

### Building and Installing Firmware from source (Option 2)(not easy)
To build the ESP32 Marauder firmware from source and install it on the Adafruit Huzzah32, follow the instructions under [Installing Firmware](installing-firmware).

## Assembling Hardware
1. Solder the male header pins included with your Adafruit Huzzah32 to the Huzzah32 board
    - *supporting image here*
2. Connect the Huzzah32 to the ESP32 Marauder Kit PCB
    - *supporting image here*
3. Connect your 3.7V LiPo battery to the JST connector of the Huzzah32
    - Note: Ensure the power switch of the ESP32 Marauder Kit PCB is in the `off` position
4. Using some sort of adhesive such as double sided tape or glue, fix the 3.7V LiPo battery to the inside of the Marauder enclosure
    - *supporting image here*
5. Using the 4 included M2.5 x 5mm screws, screw the ESP32 Marauder PCB to the enclosure so that the TFT Touch screen faces outward
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3484%20-%20Copy.jpg?raw=true" height="400">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_3485%20-%20Copy.jpg?raw=true" height="400">
</p>

## Using Your ESP32 Marauder Kit
Now that you have assembled and programmed your Adafruit Huzzah32, you should have a fully functional ESP32 Marauder. To start getting familiar with its capabilities, read through the [Applications](applications).