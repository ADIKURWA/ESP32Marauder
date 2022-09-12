# Installing Firmware via OTA

The original ESP32 Marauder firmware uses many libraries and a few IDF modifications. To avoid having to install and configure all of these libraries, this option allows the user to install a very basic firmware to the ESP32. This firmware will not involve any additional libraries or configurations and it will allow the user to install the precompiled Marauder binary via a web browser.

1. Follow the instructions under [Arduino IDE Setup](arduino-ide-setup)
2. Open the Arduino IDE
3. Plug your ESP32 into a USB port and select the COM port under `Tools`>`Port`
     - You may need to hold the "boot" button while inserting the USB
4. Select the appropriate ESP32 module under `Tools`>`Boards`
    - Select `LOLIN D32` for the following:
      - Marauder v4 (OG)
      - Marauder v6
      - Marauder Mini
    - Select `Adafruit ESP32 Feather` for the following:
      - Marauder Kit
    - Select `ESP32-S2 dev board` for the following:
      - Marauder Flipper (Flipper Zero WiFi Dev Board)
    - If you do not see this board option, ensure your Arduino IDE is on the latest version
5. For partition scheme, select `Minimal SPIFFS (Large APPS with OTA)`
    - For **Marauder Flipper**, select 16MB for `Flash Size`
6. Copy the ESP32 Marauder OTA Upload firmware source from [here](https://raw.githubusercontent.com/justcallmekoko/ESP32Marauder/master/MarauderOTA/MarauderOTA.ino) into your Arduino IDE window
7. Click the Upload button in the top left corner of the Arduino IDE and let the code compile and upload to the ESP32 Marauder
8. Download the [latest release](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) of the ESP32 Marauder firmware

| Hardware | Binary Version |
| -------- | -------------- |
| v4 (OG) | `_old_hardware.bin` |
| v6 | `_new_hardware.bin` |
| Kit | `_kit.bin` |
| Mini | `_mini.bin` |
| Flipper Zero | `_flipper.bin` |

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
    - **Wait ~60sec before restarting or removing power from the dev board**
16. Even though the device automatically reboots, press the physical RESET button before disconnecting power to force the device to hard reboot