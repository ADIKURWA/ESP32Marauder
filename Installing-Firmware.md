# Installing Firmware

If you are building your own Marauder, it will be necessary to run your own initial install of the ESP32 Marauder firmware. The following method uses the Arduino IDE. 

1. Install the [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URL to `Additional Boards Manager URLs:`
    - https://dl.espressif.com/dl/package_esp32_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
5. Install Spacehuhn's [SimpleList](https://github.com/spacehuhn/SimpleList) library in your Arduino IDE
    - Download the SimpleList repo
    - In the Arduino IDE, go to `Sketch`>`Include Library`>`Add .ZIP Library...` and add the SimpleList-master.zip you just downloaded
<!---6. Install Bodmer's [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library in your Arduino IDE--->
6. Install my fork of Bodmer's [TFT_eSPI](https://github.com/justcallmekoko/TFT_eSPI) library in your Arduino IDE
    - Download the TFT_eSPI repo
    - In the Arduino IDE, go to `Sketch`>`Include Library`>`Add .ZIP Library...` and add the TFT-eSPI-master.zip you just downloaded
    - Make the following modifications shown in [this issue](https://github.com/justcallmekoko/ESP32Marauder/issues/2#issuecomment-555695918) to the TFT_eSPI library you just installed
7. Install Bodmer's [JPEGDecoder library](https://github.com/Bodmer/JPEGDecoder)
8. Follow [these instructions](https://github.com/me-no-dev/arduino-esp32fs-plugin) for installing ESP32 Spiffs Tool
9. Install the [CH340 Drivers](https://github.com/justcallmekoko/ESP32Marauder/blob/master/Drivers/CH34x_Install_Windows_v3_4.EXE)
10. Download or clone this repository
11. Open `esp32_marauder.ino`
11.5. If you're using the analog battery measuring circuit, go to the MenuFunctions.h and change "#define BATTERY_ANALOG_ON" to 1
12. Plug your ESP32 into a USB port and select the COM port under `Tools`>`Port`
13. Select `LOLIN D32` under `Tools`>`Boards`
13.5 If you want an upscaled version of the logo, go to the data folder and rename "marauder3L1.jpg" to "marauder3L.jpg"
14. Click `ESP32 Sketch Data Upload` and wait for the SPIFFS upload to finish
15. Click the upload button