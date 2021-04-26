# IC Connections
There are several ICs which add to the ESP32 Marauder's capabilities. For newer versions of the ESP32 Marauder which feature multiple ICs, serial communication is represented in real time by an array of 0603 LEDs in the top right corner of the main PCB. The following can be found in amongst the various versions of the ESP32 Marauder:  

### ESP32 WROOM (32U)
The ESP32 serves as the main IC in the ESP32 Marauder. It drives the display, touch input, internal file system, WiFi, Bluetooth, and interchip communications. More information can be found about the ESP32 WROOM from the datasheet [here](https://datasheet.lcsc.com/lcsc/2007061615_Espressif-Systems-ESP32-WROOM-32_C82899.pdf).

#### Old ESP32 Marauder versions
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20180914_Espressif-Systems-ESP32-WROOM-32_C82899_front.jpg" width="300">
</p>

#### New ESP32 Marauder versions
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20200303_Espressif-Systems-ESP32-WROOM-32U_C328062_front.jpg" width="300">
</p>

### IP5306 / IP5306 I2C
The IP5306 and IP5306 I2C are responsible for charging the on-board lipo battery as well as supplying the electrical components of the Marauder with power. Even though the LiPo included with the marauder is 3.7v, the output voltage of the IP5306 and IP5306 I2C is boosted to 5V. More information about the battery in the ESP32 Marauder can be found at [Battery](battery). More information can be found about the IP5306 from its datasheet [here](https://datasheet.lcsc.com/lcsc/1809201029_INJOINIC-IP5306_C181692.pdf)
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20180914_INJOINIC-IP5306_C181692_front.jpg" width="300">
</p>

#### Where the IP5306 and IP5306 I2C differ
Early versions of the ESP32 Marauder used the IP5306 (non-i2c version). Battery charge levels and charging indicators were displayed to the user using a set a 4 0603 LEDs. New versions of the ESP32 Marauder use the IP5306 I2C chip which features an I2C interface on the same pins normally used for LED control. These I2C pins on the IP5306 are connected to the ESP32 on pins GPIO33 and GPIO22 as defined [here](https://github.com/justcallmekoko/ESP32Marauder/blob/master/esp32_marauder/BatteryInterface.h#L8).
```C++
#define I2C_SDA 33
#define I2C_SCL 22
```

The IP5306 I2C holds the I2C address of 0x75 defined in the firmware source as `IP5306_ADDR`.  
The following table describes the hex values returned by the IP5306 I2C and their corresponding battery levels.  
| HEX | Battery Level |
| --- | ------------- |
| 0xE0 | 25% |
| 0xC0 | 50% |
| 0x80 | 75% |
| 0x00 | 100% |

The ESP32 queries the battery level from the IP5306 I2C every 3000ms.  
The battery level is displayed on screen on the status bar. More information can be found about the status bar at [Status Bar](status-bar).

Do not try to communicate via I2C with the non-I2C version of the IP5306. It will not work.

### ESP8266
The ESP8266 is only available on certain ESP32 Marauder boards. Early versions of the ESP32 Marauder do not feature this IC. The ESP8266 is responsible for carrying out WiFi transmission operations the ESP32 is incapable of such as Deauthentication attacks. More information about the ESP8266 can be found [here](https://datasheet.lcsc.com/lcsc/2102191804_Ai-Thinker-ESP-12F-ESP8266MOD_C82891.pdf).

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20180914_Ai-Thinker-ESP-12F-ESP8266MOD_C82891_front.jpg" width="300">
</p>

The following tables describes the physical connections between the ESP32 and ESP8266
| ESP32 | ESP8266 |
| ----- | ------- |
| GPIO13 | GPIO0 |
| GPIO14 | RST |
| GPIO26 | RX |
| GPIO27 | TX |

The ESP32 and ESP8266 communicate over [HardwareSerial](https://github.com/arduino/ArduinoCore-avr/blob/master/cores/arduino/HardwareSerial.cpp)
The ESP32 sends a heart beat to the ESP8266 every 1000ms and serves as a USB-Serial proxy to update the ESP8266's firmware when needed. The ESP32 is able to reboot the ESP8266 and select its boot mode. See [ESP8266 Update](esp8266-update) for more information.

### ATmega32u4
The ATmega32u4 is only available in certain versions of the ESP32 Marauder. Early versions of the ESP32 Marauder do not feature this chip. The ATmega32u4 is responsible for executing keystroke injection attacks driven by the ESP32. More information about the keystroke injection attacks of the ESP32 Marauder can be found at [BadUSB](badusb). More information about the ATmega32u4 can be found [here](https://datasheet.lcsc.com/lcsc/1809032024_Microchip-Tech-ATMEGA32U4-MU_C112161.pdf).

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20180914_Microchip-Tech-ATMEGA32U4-MU_C112161_front_10.jpg" width="300">
</p>

The following table describes the connections made between the ESP32 and the ATmega32u4:  
| ESP32 | ATmega32u4 |
| ----- | ---------- |
| GPIO4 | RX |
| GPIO25 | TX |

The SPI interface of the ATmega32u4 is broken out at the bottom of the ESP32 Marauder to allow for ICSP.  
The ATmega32u4 is initially flashed with the Caterina bootloader and programmed over USB with the source found [here](https://github.com/justcallmekoko/ESP32Marauder/blob/master/a32u4_marauder/a32u4_marauder.ino). The ATmega32u4 firmware in this repository is heavily borrowed from [Spacehuhn's](https://github.com/spacehuhn) [WiFi Duck](https://github.com/spacehuhn/wifi_ducky/blob/master/arduino_wifi_duck/arduino_wifi_duck.ino) project.  

The ATmega32u4 is configured to use an external 16mhz crystal.

### USB2514B USB Hub
This IC is only featured on certain versions of the ESP32 Marauder. The USB2514B is responsible for allowing the CH340C and [ATmega32u4](#atmega32u4) to communicate with an external machine over USB through one USB-C port. More information about the USB2514B can be found in its datasheet [here](https://datasheet.lcsc.com/lcsc/1809200030_Microchip-Tech-USB2514B-AEZC-TR_C16251.pdf). When the ESP32 Marauder is connected to an external machine, both the CH340C and the ATmega32u4 will populate as separate serial devices.  
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://assets.lcsc.com/images/lcsc/900x900/20180914_Microchip-Tech-USB2514B-AEZC-TR_C16251_front.jpg" width="300">
</p>

### ILI9341 TFT Touch Screen
Make the following connections between your 2.8" TFT Screen and your ESP32 board. You may need to refer to a pinout sheet specific to the ESP32 dev board you have chosen. For more infomation about this circuit, please refer to [this schematic](https://github.com/justcallmekoko/ESP32Marauder/blob/master/schematics/Schematic_ESP32-Marauder-2_ESP32-Marauder-2-Schematic_20191007113616_png.png)

| SD Card | 2.8" TFT | ESP32  |
| ------- | -------- | ------ |
|         | VCC      | VCC    |
|         | GND      | GND    |
|         | CS       | GPIO17 |
|         | RESET    | GPIO5  |
|         | D/C      | GPIO16 |
| SD_MOSI | MOSI     | GPIO23 |
| SD_SCK  | SCK      | GPIO18 |
|         | LED      | GPIO32 |
| SD_MISO | MISO     | GPIO19 |
|         | T_CLK    | GPIO18 |
|         | T_CS     | GPIO21 |
|         | T_DI     | GPIO23 |
|         | T_DO     | GPIO19 |
|         | T_IRQ    |        |
| SD_CS   |          | GPIO12 |