# Arduino IDE Setup
1. Install and open the [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URLs to Additional Boards Manager URLs:
    - https://dl.espressif.com/dl/package_esp32_index.json
    - https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
    - Make sure it is version `2.0.0-rc1`