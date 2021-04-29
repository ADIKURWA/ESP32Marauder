# Status Bar
The ESP32 Marauder features a status bar used to display general system information while on the main menu or executing certain operations. 

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/marauder%20screen.jfif?raw=true" width="500">
</p>

1. [Current internal temperature](#internal-temp)
2. [Current WiFi channel](#channel)
3. [Current available memory](#memory)
4. [SD Card status](#sd-card)
5. [Battery status](#battery)
6. [Battery level](#battery)

## Battery
On the right side of the status bar, there is a battery status indicator. The color of the indicator represents the status of the battery. To the right of the battery status indicator is the current battery level represented in percent.
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/battery_16.bmp?raw=true" width="100">
</p>
The following table describes the battery status indicator and its meaning  

| Color | Status |
| ----- | ------ |
| Green | Battery level is between 25%-100% |
| Red   | Battery level is between 0%-25% |

## SD Card
On the right side of the status bar to the left of the battery status indicator is the SD card status indicator.
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/sd_16.bmp?raw=true" width="100">
</p>
The following table describes the different states of the SD card status indicator  

| Color | Status |
| ----- | ------ |
| Green | The SD card is inserted and initialized |
| Red   | The SD card is not inserted or failed to initialize |


## Memory
In the center of the status bar to the left of the SD card status indicator is the current number of available bytes of memory. As certain functions of the Marauder are used, this number with fluctuate. This is expected.

## Channel
On the left side of the status bar to the left of the available memory indicator is the current channel indicator. This represents the current channel the WiFi interface of the ESP32 is tuned to. As WiFi attacks or analysis operations are executed, this number will change.

## Internal Temp
On the far left side of the status bar is the current internal temperature indicator. As the ESP32 executes complex processes, the internal temperature will rise. The temperature is represented in Celsius. 