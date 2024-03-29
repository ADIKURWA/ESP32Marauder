# Installing Firmware From Source

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/diy.png?raw=true" width="500">
</p>

If you are building your own Marauder or assembling the ESP32 Marauder Kit, it will be necessary to run your own initial install of the ESP32 Marauder firmware. The following method uses the Arduino IDE. 

1. Follow the IDE setup instructions under [Arduino IDE Setup](arduino-ide-setup)
2. Download and install the following libraries using the ZIP library installer under `Sketch`>`Library`>`Add .ZIP Library`
    - [lv_arduino](https://github.com/lvgl/lv_arduino)
    - [LinkedList](https://github.com/ivanseidel/LinkedList)
    - [TFT_eSPI](https://github.com/justcallmekoko/TFT_eSPI)
    - [JPEGDecoder library](https://github.com/Bodmer/JPEGDecoder)
    - [NimBLE](https://github.com/h2zero/NimBLE-Arduino)
    - [NeoPixel](https://github.com/adafruit/Adafruit_NeoPixel)
    - [ArduinoJson](https://github.com/bblanchon/ArduinoJson/releases/tag/v6.18.2)
    - [SwitchLib](https://github.com/justcallmekoko/SwitchLib/releases/latest)
    - [ESPAsyncWebServer](https://github.com/bigbrodude6119/ESPAsyncWebServer)
    - [AsyncTCP](https://github.com/me-no-dev/AsyncTCP)
<!---6. Install Bodmer's [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library in your Arduino IDE--->
3. Follow [these instructions](https://github.com/me-no-dev/arduino-esp32fs-plugin) for installing ESP32 Spiffs Tool
4. Install the [CH340 Drivers](https://github.com/justcallmekoko/ESP32Marauder/blob/master/Drivers/CH34x_Install_Windows_v3_4.EXE)
5. Download or clone this repository
6. Open `esp32_marauder.ino` in your Arduino IDE
    - If you're using the analog battery measuring circuit, go to the MenuFunctions.h and change "#define BATTERY_ANALOG_ON" to 1
7. Define your hardware version with the [following lines](https://github.com/justcallmekoko/ESP32Marauder/blob/master/esp32_marauder/configs.h#L7) in `config.h`. To determine which version you posses, see [Marauder Versions](marauder-versions) 

8. Plug your ESP32 into a USB port and select the COM port under `Tools`>`Port`
9. Select the appropriate ESP32 module under `Tools`>`Boards`
    - Select `LOLIN D32` for the following:
      - Marauder v4 (OG)
      - Marauder v6
      - Marauder Mini
    - Select `Adafruit ESP32 Feather` for the following:
      - Marauder Kit
    - Select `ESP32-S2 dev board` for the following:
      - Marauder Flipper (Flipper Zero WiFi Dev Board)
10. For partition scheme, select `Minimal SPIFFS (Large APPS with OTA)`
11. Click `ESP32 Sketch Data Upload` and wait for the SPIFFS upload to finish
12. Copy my [User_Setup.h](https://github.com/justcallmekoko/ESP32Marauder/blob/master/User_Setup.h) into your TFT_eSPI library folder to replace the one already in there
13. Click the upload button