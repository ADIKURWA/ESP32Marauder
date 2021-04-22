# IC Connections
There are several ICs which add to the ESP32 Marauder's capabilities. The following can be found in amongst the various versions of the ESP32 Marauder:  

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