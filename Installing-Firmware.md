# Installing Firmware

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/diy.png?raw=true" width="500">
</p>

If you are building your own Marauder or assembling the ESP32 Marauder Kit, it will be necessary to run your own initial install of the ESP32 Marauder firmware. The following method uses the Arduino IDE. 

1. Install and open the [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URL to `Additional Boards Manager URLs:`
    - https://dl.espressif.com/dl/package_esp32_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
5. Download and install the following libraries using the ZIP library installer under `Sketch`>`Library`>`Add .ZIP Library`
    - [lv_arduino](https://github.com/lvgl/lv_arduino)
    - [LinkedList](https://github.com/ivanseidel/LinkedList)
    - [TFT_eSPI](https://github.com/justcallmekoko/TFT_eSPI)
    - [JPEGDecoder library](https://github.com/Bodmer/JPEGDecoder)
    - [NimBLE](https://github.com/h2zero/NimBLE-Arduino)
    - [NeoPixel](https://github.com/adafruit/Adafruit_NeoPixel)
    - [ArduinoJSON](https://github.com/bblanchon/ArduinoJson/releases/tag/v5.13.5) **v5.13.5**
<!---6. Install Bodmer's [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library in your Arduino IDE--->
6. Follow [these instructions](https://github.com/me-no-dev/arduino-esp32fs-plugin) for installing ESP32 Spiffs Tool
7. Install the [CH340 Drivers](https://github.com/justcallmekoko/ESP32Marauder/blob/master/Drivers/CH34x_Install_Windows_v3_4.EXE)
8. Download or clone this repository
9. Open `esp32_marauder.ino` in your Arduino IDE
    - If you're using the analog battery measuring circuit, go to the MenuFunctions.h and change "#define BATTERY_ANALOG_ON" to 1
10. Find the [following lines](https://github.com/justcallmekoko/ESP32Marauder/blob/master/esp32_marauder/Display.h#L49) in `Display.h` and change them according to your hardware version. to determine which version you posses, see [Marauder Versions](marauder-versions) 
```C++
// EXAMPLE
#define TFT_SHIELD
#define TFT_DIY
#define KIT
```
```C++
// For original ESP32 Marauder
#define TFT_SHIELD
//#define TFT_DIY
//#define KIT
```
```C++
// For ESP32 Marauder v6
//#define TFT_SHIELD
#define TFT_DIY
//#define KIT
```
```C++
// For ESP32 Marauder Kit
//#define TFT_SHIELD
#define TFT_DIY
#define KIT
```

11. Plug your ESP32 into a USB port and select the COM port under `Tools`>`Port`
12. Select the appropriate ESP32 module under `Tools`>`Boards`
    - If you are using the original ESP32 Marauder: `LOLIN D32`
    - If you are using the ESP32 Marauder V6: `LOLIN D32`
    - If you are using the ESP32 Marauder Kit: `Adafruit ESP32 Feather`
13. For partition scheme, select `Minimal SPIFFS (Large APPS with OTA)`
14. Click `ESP32 Sketch Data Upload` and wait for the SPIFFS upload to finish
15. Copy my [User_Setup.h](https://github.com/justcallmekoko/ESP32Marauder/blob/master/User_Setup.h) into your TFT_eSPI library folder to replace the one already in there
16. Click the upload button