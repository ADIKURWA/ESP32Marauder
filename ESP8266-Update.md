# ESP8266 Update
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/esp_update.bmp?raw=true" width="100">
</p>
**This feature is only available on the ESP32 Marauder Centauri and ESP32 Marauder 7. For more information on the two devices, see [Marauder Versions](marauder-versions).**  
The ESP32 operates as a serial proxy between a host PC and the ESP8266. When a new version of the ESP8266 firmware is released and an update is available, the following steps will need to be taken in order to properly update the firmware of the ESP8266.  

1. Connect the ESP32 Marauder to your PC via USB and open [this project](https://github.com/justcallmekoko/ESP32Marauder/tree/master/esp8266_marauder) in your Arduino IDE
2. On the ESP32 Marauder, navigate to `Device`>`Update Firmware`>`ESP8266 Update`
    - The ESP32 will automatically place the ESP8266 in "program" mode
3. In the Arduino IDE, make sure the following options are set
    - Board: Generic ESP8266 Module
    - Flash Mode: DOUT
    - Baud Rate: 57600
    - Reset Method: no dtr
4. Hit the Upload button in the Arduino IDE
5. Once the firmware upload is complete, you can hit `Back` on the ESP32 Marauder to return to the menu